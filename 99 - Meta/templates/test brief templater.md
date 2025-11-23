<%*
let bedrijf = await tp.system.prompt("Bedrijfsnaam")
let contactpersoon = await tp.system.prompt("Contactpersoon")
let functie = await tp.system.prompt("Stagefunctie")
let bron = await tp.system.prompt("Waar vond je de vacature?")
let reden = await tp.system.prompt("Waarom dit bedrijf?")
-%>

Onderwerp: Stageaanvraag – <%= functie %>

Beste <%= contactpersoon %>,

Graag solliciteer ik bij <%= bedrijf %> naar een stageplek als <%= functie %>, zoals vermeld op <%= bron %>. 

Wat mij aanspreekt in <%= bedrijf %> is <%= reden %>.

Met vriendelijke groet,  
{{jouw naam}}
