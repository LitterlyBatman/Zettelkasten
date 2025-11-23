---
topic: gym
---


```dataviewjs
// === CONFIG ===
const SHOW_COLOR_STRIPE = false;   // verticale kleurstreep links
const COLOR_TEXT = true;         // spiergroep tekst kleuren

const databaseFile = "oefeningen";

// === KLEUREN PER SPIERGROEP ===
const COLORS = {
	"Chest": "#52eea3",
	"Back": "#54b6f8",
	"Legs": "#437cf3",
	"Shoulders": "#9446f8",
	"Arms": "#c952ed",
	"Core": "#e54f9b",
	"Abs": "#e3365e"
};

// === DATA OPHALEN ===
const file = dv.page(databaseFile);
if (!file || !file.oefeningen) {
	dv.el("p", "⚠️ Geen oefeningen gevonden — check je YAML bestand.");
}
const data = file?.oefeningen ?? [];

// === FILTER UI ===
const filterContainer = dv.el("div", "", { cls: "filters" });

function makeSelect(label, key) {
	const wrap = document.createElement("label");
	wrap.textContent = label + ": ";
	const select = document.createElement("select");

	select.innerHTML =
		`<option value="">(alle)</option>` +
		[...new Set(data.map(x => x[key]))]
			.filter(Boolean)
			.sort()
			.map(v => `<option value="${v}">${v}</option>`)
			.join("");

	wrap.appendChild(select);
	filterContainer.appendChild(wrap);
	return select;
}

const spiergroepSelect = makeSelect("Spiergroep", "spiergroep");
const typeSelect = makeSelect("Type", "type");
const moeilijkheidSelect = makeSelect("Moeilijkheid", "moeilijkheid");
const equipmentSelect = makeSelect("Equipment", "equipment");

// === ZOEKVELD ===
const searchWrap = document.createElement("label");
searchWrap.textContent = "Zoek: ";
const searchInput = document.createElement("input");
searchInput.type = "text";
searchInput.placeholder = "zoek op naam...";
searchWrap.appendChild(searchInput);
filterContainer.appendChild(searchWrap);

// === TABELCONTAINER ===
const tableContainer = dv.el("div", "", { cls: "table" });

// === TABEL RENDEREN ===
function renderTable() {
	const filters = {
		spiergroep: spiergroepSelect.value,
		type: typeSelect.value,
		moeilijkheid: moeilijkheidSelect.value,
		equipment: equipmentSelect.value,
		search: searchInput.value.toLowerCase()
	};

	const filtered = data.filter(item =>
		(!filters.spiergroep || item.spiergroep === filters.spiergroep) &&
		(!filters.type || item.type === filters.type) &&
		(!filters.moeilijkheid || item.moeilijkheid === filters.moeilijkheid) &&
		(!filters.equipment || item.equipment === filters.equipment) &&
		(!filters.search || item.naam.toLowerCase().includes(filters.search))
	);

	tableContainer.innerHTML = "";

	const table = document.createElement("table");
	table.style.width = "100%";
	table.style.borderCollapse = "collapse";

	// HEADERS
	const thead = table.createTHead();
	const headerRow = thead.insertRow();
	["", "Naam", "Spiergroep", "Type", "Moeilijkheid", "Equipment"]
		.forEach(h => {
			const th = document.createElement("th");
			th.textContent = h;
			th.style.padding = "6px";
			th.style.borderBottom = "1px solid #444";
			headerRow.appendChild(th);
		});

	// BODY
	const tbody = table.createTBody();

	filtered.forEach(item => {
		const row = tbody.insertRow();
		const color = COLORS[item.spiergroep] || "#888";

		// Optie A: vertical stripe
		const stripeCell = row.insertCell();
		stripeCell.style.width = "6px";
		stripeCell.style.height = "2px";
		stripeCell.style.backgroundColor = SHOW_COLOR_STRIPE ? color : "transparent";

		// Overige cellen
		const cells = [
			item.naam,
			item.spiergroep,
			item.type,
			item.moeilijkheid,
			item.equipment
		];

		cells.forEach((val, idx) => {
			const cell = row.insertCell();
			cell.textContent = val;
			cell.style.padding = "5px";

			// Optie B: spiergroep tekst kleuren
			if (idx === 1 && COLOR_TEXT) {
				cell.style.color = color;
				cell.style.fontWeight = "600";
			}
		});
	});

	tableContainer.appendChild(table);
}

[spiergroepSelect, typeSelect, moeilijkheidSelect, equipmentSelect, searchInput]
	.forEach(el => el.addEventListener("input", renderTable));

renderTable();
```

