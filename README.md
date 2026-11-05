# Séance 1 — Partage de frais

## 1. Déroulé de la séance

| Temps | Étape |
| :--- | :--- |
| 10 min | Présentation du projet et de GitHub |
| 10 min | Création du dépôt et installation |
| 95 min | Réalisation, comme d'habitude |
| 5 min | Clôture |

---

## 2. Ce que l'application doit faire

Un groupe d'amis part une semaine en vacances. Chacun paie des choses pour les autres, les tickets s'accumulent, et à la fin plus personne ne sait qui doit combien à qui. L'application note les dépenses et fait les comptes à tout moment.

### Demandes de l'application

* **Données :**
  * Groupe : nom, dates du séjour, membres.
  * Dépense : libellé, montant, date, payeur, participants.
* **Fonctionnalités :**
  * Créer un groupe et ses membres.
  * Ajouter ou supprimer une dépense.
  * Afficher le solde de chaque membre.
* **Règles :**
  * Une dépense a un montant positif et au moins un participant.
  * Le payeur et les participants appartiennent au groupe.
  * La date d'une dépense est comprise dans le séjour, dates de début et de fin incluses.
  * Une dépense est partagée à parts égales entre ses participants. Le centime restant va au premier participant ajouté.
  * Les soldes sont exacts au centime près et leur somme vaut toujours 0.
* **Si vous avez fini :**
  * Modifier une dépense.
  * Filtrer les dépenses par membre ou par période.
  * Exporter en CSV.

---

## 3. Cas de vérification

Exemple de groupe : **Alice**, **Bob** et **Chloé**. *(Les lignes s'enchaînent)*

| Action | Résultat attendu |
| :--- | :--- |
| Alice paie 30 € pour Alice, Bob et Chloé | Alice +20,00 ; Bob -10,00 ; Chloé -10,00 |
| Une dépense datée hors du séjour | Refusée, soldes inchangés |
| Une dépense de 0 € | Refusée, soldes inchangés |
| Sur un nouveau groupe, Alice paie 10 € pour les trois | Alice +6,66 ; Bob -3,33 ; Chloé -3,33 |
