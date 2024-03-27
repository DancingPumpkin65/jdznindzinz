```php
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $couleur = $_POST['couleur'];
    
    $couleursDescriptions = [
        "rouge" => "La couleur rouge symbolise la passion et l'énergie.",
        "bleu" => "Le bleu est souvent associé à la sérénité et à la tranquillité.",
        "vert" => "Le vert est la couleur de la nature et de la croissance.",
        "jaune" => "Le jaune est synonyme de joie et d'énergie positive."
    ];
    
    if (array_key_exists($couleur, $couleursDescriptions)) {
        echo "<p>" . $couleursDescriptions[$couleur] . "</p>";
    } else {
        echo "<p>La couleur spécifiée n'a pas de description associée.</p>";
    }
}
```
