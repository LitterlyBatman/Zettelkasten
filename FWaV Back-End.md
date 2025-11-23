---
topic: software-docu
---

 2025 - 09 - 09 09:35

tags: [[Fashion with a view]]

progress: >

# FWaV Back-End

de backend van FWaV gebruikt drie kolommen als volgt

1️⃣ `users`  
2️⃣ `magazines`  
3️⃣ `pages`

##  **1. Tabel: `users`**
---

Bevat alle accounts die kunnen inloggen in het systeem — alleen `developer` en `user`.

| Kolomnaam    | Type                          | Beschrijving                              | Voorbeeldwaarde       |
| ------------ | ----------------------------- | ----------------------------------------- | --------------------- |
| `id`         | INT UNSIGNED (AUTO_INCREMENT) | Unieke ID van de gebruiker                | 1                     |
| `username`   | VARCHAR(255)                  | Inlognaam (moet uniek zijn)               | `"admin_user"`        |
| `password`   | VARCHAR(255)                  | Wachtwoord in platte tekst                | `"admin123"`          |
| `role`       | ENUM('developer','user')      | Rol bepaalt rechten in admin panel        | `"developer"`         |
| `created_at` | DATETIME                      | Datum/tijd waarop gebruiker is aangemaakt | `2025-10-07 12:30:00` |
```scss
┌───────────────────────────────────────────┐
│                 users                     │
├────────────┬───────────────┬──────────────┤
│ id         │ INT (PK)      │              │
│ username   │ VARCHAR(255)  │ Uniek        │
│ password   │ VARCHAR(255)  │ Wachtwoord   │
│ role       │ ENUM          │ 'user'/'developer' │
│ created_at │ DATETIME      │              │
└────────────┴───────────────┴──────────────┘
```

## :LiBook: **2. Tabel: `magazines`**
---

	Deze tabel bevat de magazines, dez

###  Beschrijving

| Kolomnaam     | Type                          | Beschrijving                                  | Voorbeeldwaarde              |
| ------------- | ----------------------------- | --------------------------------------------- | ---------------------------- |
| `id`          | INT UNSIGNED (AUTO_INCREMENT) | Uniek ID van het magazine                     | 1                            |
| `title`       | VARCHAR(255)                  | Naam van het magazine                         | `"placeholder"`              |
| `description` | TEXT                          | Korte beschrijving van de inhoud (voor admin) | `"placeholder beschrijving"` |
| `created_at`  | DATETIME                      | Wanneer het magazine is aangemaakt            | `2069-04-20 12:00:00`        |

``` scss
┌───────────────────────────────────────┐
│              magazines                │
├────────────┬───────────────┬──────────┤
│ id         │ INT (PK)      │ 🔢       │
│ title      │ VARCHAR(255)  │ 📖 Naam  │
│ description│ TEXT          │ 📝 Info  │
│ created_at │ DATETIME      │ ⏰       │
└────────────┴───────────────┴──────────┘
```

📌 **Gebruik in de app:**

-admins beheren content magazine via admin panel
-elke magazine bevat minimaal 1 of meerdere pagina's
-de eerste pagina in de `array` word de cover


## :FarNewspaper: **3. Tabel: `pages`**
---

Bevat de **individuele pagina’s** (afbeeldingen) binnen elk magazine.

### Beschrijving

|Kolomnaam|Type|Beschrijving|Voorbeeldwaarde|
|---|---|---|---|
|`id`|INT UNSIGNED (AUTO_INCREMENT)|Unieke ID van de pagina|1|
|`magazine_id`|INT UNSIGNED (FK)|Verwijst naar `magazines.id`|1|
|`page_number`|INT|Paginanummer binnen het magazine|1|
|`image_path`|VARCHAR(255)|Pad naar de afbeelding|`'/uploads/mag1/cover.jpg'`|
|`is_cover`|TINYINT(1)|1 = coverpagina, 0 = gewone pagina|1|
|`created_at`|DATETIME|Datum/tijd waarop pagina is toegevoegd|`2025-10-07 12:45:00`|
```scss
┌──────────────────────────────────────────────────────────────┐
│                           pages                              │
├────────────┬─────────────────────┬───────────────────────────┤
│ id         │ INT (PK)            │ 🔢                        │
│ magazine_id│ INT (FK) → magazines│ 🔗 Linkt naar magazine    │
│ page_number│ INT                 │ 📄 Volgorde van pagina's  │
│ image_path │ VARCHAR(255)        │ 🖼️ Bestandspad afbeelding │
│ is_cover   │ TINYINT(1)          │ 🎨 1 = cover, 0 = normaal │
│ created_at │ DATETIME            │ ⏰                        │
└────────────┴─────────────────────┴───────────────────────────┘

```

## 🔗 `Entity Relation Diagram`
---

```bash
         ┌────────────┐
         │   users    │
         └──────┬─────┘
                │
   (beheerd via admin panel)
                │
         ┌──────┴──────┐
         │  magazines  │
         └──────┬──────┘
                │ 1:N
                │
         ┌──────┴──────┐
         │   pages     │
         └─────────────┘
```

> User `(developer/admin)` beheert meerdere magazines
> Eén magazine bevat meerdere pagina's
> Elke page verwijst via `magazine_id` terug naar zijn magazine

# Structuur werking

| magazines.id | title           |
| ------------ | --------------- |
| 1            | “Oktober 2025”  |
| 2            | “November 2025” |

| pages.id | magazine_id | page_number | image_path             | is_cover |
| -------- | ----------- | ----------- | ---------------------- | -------- |
| 1        | 1           | 1           | /uploads/okt/page1.jpg | 1        |
| 2        | 1           | 2           | /uploads/okt/page2.jpg | 0        |
| 3        | 2           | 1           | /uploads/nov/page1.jpg | 1        |
## 🧠 Wat dit betekent in de praktijk

Elke **magazine** is dus eigenlijk een **“container”** voor één editie van je content — denk aan één volledig tijdschrift, met alle pagina’s erin.  
➡️ De **pages** zijn de “inhoud” van dat magazine.

Dat betekent:

- Als jij **een nieuw magazine aanmaakt**, maak je eigenlijk een nieuwe _editie_ (met een nieuwe `magazines`-rij).
    
- En daarna voeg je **pages** toe die eraan gekoppeld zijn via `magazine_id`.

```bash
┌───────────────────────┐
│       magazines       │
│  id | title | create  │
└──────────┬────────────┘
           │
           │ 1:N
           │
┌──────────┴─────────────┐
│         pages          │
│ id | magazine_id | img │
└────────────────────────┘

```

## :LiImport: SQL import
---
De SQL file is zo gestructureerd dat ook als je al een 

```SQL
-- drop if duplicate

CREATE DATABASE IF NOT EXISTS `fwav` CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;

USE `fwav`;

-- user table

DROP TABLE IF EXISTS `users`;

CREATE TABLE `users` (

  `id` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT,

  `username` VARCHAR(255) NOT NULL UNIQUE,

  `password` VARCHAR(255) NOT NULL,

  `created_at` DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,

  PRIMARY KEY (`id`)

) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

-- magazine table

DROP TABLE IF EXISTS `magazines`;

CREATE TABLE `magazines` (

  `id` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT,

  `title` VARCHAR(255) NOT NULL,

  `description` TEXT,

  `archived` TINYINT(1) NOT NULL DEFAULT 0,

  `created_at` DATE NOT NULL DEFAULT CURRENT_TIMESTAMP,

  PRIMARY KEY (`id`)

) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

-- pages table

DROP TABLE IF EXISTS `pages`;

CREATE TABLE `pages` (

  `id` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT,

  `magazine_id` INT(10) UNSIGNED NOT NULL,

  `page_number` INT(10) NOT NULL,

  `image_path` VARCHAR(255) NOT NULL,

  `created_at` DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,

  PRIMARY KEY (`id`),

  KEY `idx_magazine_id` (`magazine_id`),

  CONSTRAINT `fk_pages_magazine` FOREIGN KEY (`magazine_id`) REFERENCES `magazines`(`id`) ON DELETE CASCADE

) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
```

```
[Header / Hero]   ← section 1
      ↓
[Main Content]    ← section 2
      ↓
[Closing / Contact / Footer] ← section 3
```
