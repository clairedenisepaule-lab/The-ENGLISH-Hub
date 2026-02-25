# 🎮 The English Hub — Intégration des jeux

## Ce qui a été modifié dans index.html

Deux modifications ont été apportées à l'`index.html` :

### 1. Nouveaux styles CSS ajoutés (après `.ws-view`)
Une section `.games-section` avec ses styles : bannière violette visible, bouton ▶ Play, hover effects. Rien d'autre n'a été touché dans le CSS.

### 2. Nouvelle logique JS (dans le bloc `<script>` principal)
- Ajout d'un objet `gamesData` : c'est **ici qu'on ajoute les futurs jeux**
- Ajout d'une fonction `renderGamesSection()` qui génère le bloc jeux
- Modification de `openMagDetail()` : la section 🎮 Games s'injecte **entre la description/Canva et les worksheets**

---

## Structure des fichiers à mettre en place sur GitHub

```
mon-repo/
├── index.html                          ← remplacer par le fichier modifié
└── jeux/
    └── whack_a_word_nomad_kitchen.html ← nouveau fichier à déposer
```

---

## Comment ajouter un nouveau jeu plus tard

Dans l'objet `gamesData` en JS, ajouter une entrée :

```js
const gamesData = {
  'agora': {
    'U5': [
      { name:'Whack-a-Word', emoji:'⚡', meta:'Vocabulaire · The Nomad Kitchen · 12 mots', file:'jeux/whack_a_word_nomad_kitchen.html' },
      // Ajouter ici le prochain jeu pour AGORA U5
    ]
  },
  // Exemple pour une autre classe :
  'cap': {
    'U1': [
      { name:'Pendu', emoji:'🪢', meta:'Vocabulaire · Healthy ME!', file:'jeux/hangman_cap_u1.html' },
      { name:'Mots croisés', emoji:'🔤', meta:'Vocabulaire · Healthy ME!', file:'jeux/crossword_cap_u1.html' },
    ]
  }
};
```

Les clés correspondent aux classes : `'cap'`, `'mbbe'`, `'mrc'`, `'agora'`, `'bts'`
Les numéros de séquence : `'U1'`, `'U2'`, `'U3'`, etc.

---

## Placement du bouton ▶ Play

Le bloc 🎮 Games s'affiche dans la vue détail d'une séquence (après avoir cliqué sur une carte séquence), dans cet ordre :
1. Image de la séquence
2. Description
3. Vidéo (si présente)
4. Présentation Canva (si présente)
5. **🎮 GAMES ← ici, bien visible avant les worksheets**
6. 📁 Documents
7. 📄 Worksheets

---

## Fichiers fournis

| Fichier | Destination |
|---|---|
| `index.html` | Racine du repo (remplace l'ancien) |
| `whack_a_word_nomad_kitchen.html` | `/jeux/` |
| `hangman_b1.html` | `/jeux/` (disponible, pas encore lié) |
| `crossword_b1.html` | `/jeux/` (disponible, pas encore lié) |
