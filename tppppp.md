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

SELECT numEtu, 
    TIMESTAMPDIFF(YEAR, 
        STR_TO_DATE(dateNaissance, '%d/%m/%Y'), 
        CURDATE()
    ) AS age 
FROM ETUDIANT;

SELECT MAX(prixForm) AS prixMax, MIN(prixForm) AS prixMin FROM FORMATION;

SELECT SUM(prixForm) AS total_paiement FROM FORMATION;

SELECT codeSess0, COUNT(*) AS nombreEtudiantsInscrits FROM INSCRIPTION GROUP BY codeSess0;

SELECT DISTINCT numCINEtu0 FROM INSCRIPTION;

SELECT numCINEtu0, COUNT(*) AS nombreInscriptions FROM INSCRIPTION GROUP BY numCINEtu0;

-- Methode1
SELECT codeSess0, 
       SUM(CASE WHEN typeCours = 'Distanciel' THEN 1 ELSE 0 END) AS inscriptionsDistancielles, 
       SUM(CASE WHEN typeCours = 'Présentiel' THEN 1 ELSE 0 END) AS inscriptionsPresentielles 
FROM INSCRIPTION 
GROUP BY codeSess0;
--Methode2
SELECT codeSess0, 
       COUNT(CASE WHEN typeCours = 'Distanciel' THEN 1 END) AS inscriptionsDistancielles,
       COUNT(CASE WHEN typeCours = 'Présentiel' THEN 1 END) AS inscriptionsPresentielles 
FROM INSCRIPTION 
GROUP BY codeSess0;

```
