---
topic: software-docu
---

**# Todo Website 

## Inhoudsopgave  
1. [Overzicht](#overzicht)  
2. [Architectuur en Technologieën](#architectuur-en-technologieën)  
3. [Installatie en Setup](#installatie-en-setup)  
4. [Gebruik](#gebruik)  
5. [API-documentatie](#api-documentatie)  
6. [Best Practices](#best-practices)  
7. [Contributie en Development Workflow](#contributie-en-development-workflow)  
8. [Bekende Problemen en Oplossingen](#bekende-problemen-en-oplossingen)  
9. [Licentie](#licentie)  

---

## Overzicht  
- **Doel van het project:**
  > het doel van het creeeren van een simpele todowebsite is het oefenen met het bouwen cvan websites, neem back end en frontend
- **Belangrijkste functies:**  
  -taken toevoegen
  -taken verwijderen
  -taken aanpassen
  -taken afvinken

- **Status van het project:**  
- **Relevante documentatie:**  

---

## Architectuur en Technologieën  
- **Backend:**  
- **Frontend:**  
- **Database:**  
- **Hosting en Deployment:**  
- **Structuur van de codebase:**  

---

## Installatie en Setup  

- local hosting service (MAMP
- 

### Dependencies

```bash
# Voorbeeld: Installeer dependencies
npm install
```

## Database

>  creating a the todo item tabel
```php
CREATE TABLE todos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT,
    is_done BOOLEAN DEFAULT FALSE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```
- title - korte omschrijving taak, titel
- description - kleine uitleg bij taak
- is_done - boolean die check of de taak is gedaan
- created_at - tijd en datum van creeren taak

> creating a user profile table
```php
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```
- 

> kopellen van users aan todo item
```php 
ALTER TABLE todos ADD user_id INT,
ADD FOREIGN KEY (user_id) REFERENCES users(id);

```
- 