# Battute.json

Repository minimale che contiene un archivio in formato JSON con oltre un centinaio di battute e giochi di parole in italiano. Il file `battute.json/battute.json` è pensato come fonte dati riutilizzabile per bot Discord, skill vocali, applicazioni web oppure per piccoli esperimenti di NLP dedicati all'umorismo.

## Contenuto del dataset

- `jokes`: array di stringhe, ognuna corrisponde a una battuta autonoma.
- Il formato è plain text UTF-8; non vengono usati campi aggiuntivi (autore, categoria, ecc.) per restare compatibile con strumenti semplici.
- Le battute puntano a un tono leggero e adatto a un pubblico generalista; verifica comunque l'aderenza al tuo contesto prima di usarle automaticamente.

## Come usare il file

1. Copia il file nella tua applicazione o aggiungi questo repository come submodule/subtree.
2. Carica il JSON con il linguaggio che preferisci. Esempio in Node.js:

```js
import { readFileSync } from 'node:fs';

const file = readFileSync('battute.json/battute.json', 'utf8');
const { jokes } = JSON.parse(file);

// Estrai una battuta casuale
const randomJoke = jokes[Math.floor(Math.random() * jokes.length)];
console.log(randomJoke);
```

3. (Opzionale) Implementa filtri, categorie o tagging se ti servono regole personalizzate.

