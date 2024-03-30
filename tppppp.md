```sql
-- Exo 5
USE centre_formation;

SELECT * FROM Centre_formation.table_name;

SELECT * FROM Etudiant WHERE villeEtu = 'Tanger';

SELECT * FROM Formation WHERE prixForm > 3000;

SELECT titreForm, prixForm / dureeForm AS prixJournalier FROM Formation;

SELECT * FROM formation WHERE codeForm = 11;

SELECT numCINEtu0 FROM Inscription WHERE codeSess0 = 1302 ORDER BY numCINEtu0 ASC;

SELECT * FROM Specialite WHERE Active = 1;
```

```sql
-- Exo6
USE centre_formation;

SELECT COUNT(*) AS nombre_etudiants FROM ETUDIANT;
```
