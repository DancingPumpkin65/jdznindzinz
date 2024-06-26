```javascript
class Livre {
    constructor(titre = "Sans titre", genre = "Fiction", auteur = "Sans auteur", lu = false, dateLecture = null) {
        this.titre = titre;
        this.genre = genre;
        this.auteur = auteur;
        this.lu = lu;
        this.dateLecture = dateLecture ? new Date(dateLecture) : null;
    }
}

You can copy and paste this code directly into your Markdown file on GitHub.

class ListeLivres {
    constructor(livres = []) {
        if (!Array.isArray(livres)) {
            livres = [];
        }
        this.tousLivres = livres;

        if (this.tousLivres.length > 0) {
            this.tousLivres.forEach(livre => this.ajouter(livre));
        }
    }

    ajouter(livre) {
        this.tousLivres.push(livre);
    }

    terminerLivreEnCours() {
        if (this.livreEnCours) {
            this.livreEnCours.lu = true;
            this.dernierLivre = this.livreEnCours;
            this.livreEnCours = this.livreSuivant;
        } else {
            console.log("Il faut se mettre à la lecture");
        }
    }

    retirerLivre(titre) {
        this.tousLivres = this.tousLivres.filter(livre => livre.titre !== titre);
    }

    nombreLivresLu() {
        return this.tousLivres.filter(livre => livre.lu === true).length;
    }

    nombreLivresNonLu() {
        return this.tousLivres.filter(livre => livre.lu === false).length;
    }

    livreSuivant() {
        const index = this.tousLivres.findIndex(livre => !livre.lu);
        if (index !== -1) {
            return this.tousLivres[index+1];
        } else {
            return null;
        }
    }
    
    livreEnCours() {
        return this.livreEnCours;
    }
}

let livre1 = new Livre("Bader", "Fiction", "Auteur 1", true, new Date());
let livre2 = new Livre("Aymane", "Non-fiction", "Auteur 2", true);
let livre3 = new Livre("Mohamed", "Fiction", "Auteur 3", false);
let livre4 = new Livre("Ouil", "Fiction", "Auteur 3", false);
let livre5 = new Livre("Chay", "Fiction", "Auteur 3", false);

let listeLivres = new ListeLivres();
listeLivres.ajouter(livre1);
listeLivres.ajouter(livre2);
listeLivres.ajouter(livre3);
listeLivres.ajouter(livre4);
listeLivres.ajouter(livre5);

console.log(listeLivres);

listeLivres.terminerLivreEnCours();
console.log(listeLivres);

console.log("Nombre de livres lus:", listeLivres.nombreLivresLu());
console.log("Nombre de livres non luss:", listeLivres.nombreLivresNonLu());

console.log("Livre en cours:", listeLivres.livreEnCours());
console.log("Livre suivant:", listeLivres.livreSuivant());

listeLivres.retirerLivre("Aymane");
console.log(listeLivres);


let livre1 = new Livre("Bader", "Fiction", "Auteur 1", true, new Date());
let livre2 = new Livre("Aymane", "Non-fiction", "Auteur 2", true);
let livre3 = new Livre("Mohamed", "Fiction", "Auteur 3", false);
let livre4 = new Livre("Ouil", "Fiction", "Auteur 3", false);
let livre5 = new Livre("Chay", "Fiction", "Auteur 3", false);

let listeLivres = new ListeLivres();
listeLivres.ajouter(livre1);
listeLivres.ajouter(livre2);
listeLivres.ajouter(livre3);
listeLivres.ajouter(livre4);
listeLivres.ajouter(livre5);

console.log(listeLivres);

listeLivres.terminerLivreEnCours();
console.log(listeLivres);

console.log("Nombre de livres lus:", listeLivres.nombreLivresLu());
console.log("Nombre de livres non luss:", listeLivres.nombreLivresNonLu());

console.log("Livre en cours:", listeLivres.livreEnCours());
console.log("Livre suivant:", listeLivres.livreSuivant());

listeLivres.retirerLivre("Aymane");
console.log(listeLivres);
```
