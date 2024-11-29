## DB

|Nome |
|------------ |
|Alessio |
|Claudio |
|Andrea |
|Alessandro |

#### La forma normale di una colonna con soli nomi di persona dipende da come è strutturata all'interno di un database e da quali altre informazioni sono presenti.

#### Se la colonna contiene solo nomi completi: Potrebbe essere considerata in Prima Forma Normale (1FN), a patto che ogni cella contenga un singolo valore atomico (cioè un nome completo).

#### Se la colonna contiene nomi e cognomi separati: Sarebbe meglio separarli in due colonne distinte per rispettare la 1FN e facilitare le query.

### Perché la forma normale è importante?

#### Elimina ridondanze: Evita di duplicare le informazioni, risparmiando spazio e migliorando l'integrità dei dati.

#### Facilità le query: Permette di estrarre i dati in modo più efficiente e preciso.

#### Migliora la manutenibilità: Rende il database più facile da modificare e aggiornare.

### In che forma é?
#### Sarà in 2FN ? Credo di si!

|Nome |Eta |
|------------ |------------ |
|Alessio |20 |
|Andrea |40 |
|Vito |35 |
|Gloria |62 |

#### 1 FN?
#### Se ogni riga rappresenta una persona unica: ovvero, ogni nome è associato a una sola età, allora la tabella è in 1FN. Questa è la forma normale più basilare e richiede che ogni cella contenga un singolo valore atomico.

#### Se ci sono nomi duplicati con età diverse: la tabella non è in 1FN perché una cella (il nome) contiene più informazioni. In questo caso, sarebbe necessario aggiungere una colonna identificativa unica per ogni persona

#### 2 FN?

#### Se l'età dipende completamente dal nome: ovvero, ogni nome ha un'età associata e non ci sono altri attributi che dipendono solo da una parte della chiave (in questo caso, il nome), allora la tabella è anche in 2FN.

#### Se ci sono altri attributi che dipendono solo da una parte della chiave: ad esempio, se hai una colonna "Città di nascita" e la città dipende solo dal cognome (che fa parte del nome completo), allora la tabella non è in 2FN. Dovresti creare una tabella separata per le città di nascita.

### Regola della Terza Forma Normale?
#### Se non ci sono dipendenze funzionali transitive: ovvero, se non ci sono attributi che dipendono da altri attributi non chiave, allora la tabella è in 3FN.

#### Sintesi
#### 1FN: Ogni cella contiene un singolo valore atomico e non ci sono gruppi di valori ripetuti.
#### 2FN: Tutti gli attributi non chiave dipendono dalla chiave primaria intera.
#### 3FN: Non ci sono dipendenze funzionali transitive.

### In che forma è?
#### In 2 FN. Perchè? Basta leggere sotto!

|Nome |Eta |Data di nascita |
|------------ |------------ |------------ |
|Alessio |36 |10-05-1988 |
|Luca |38 |08-10-1986 |
|Andrea |38 |02-10-1986 |
|Vito |41 |02-10-1983 |

#### 1 FN?
#### Condizione: Ogni cella deve contenere un singolo valore atomico.
#### Nel tuo caso: Se ogni riga rappresenta una persona unica e i valori nelle celle sono singoli (cioè, non hai liste di nomi o date multiple in una stessa cella), allora la tua tabella è in 1FN.

#### 2 FN?
#### Condizione: La tabella deve essere in 1FN e ogni attributo non chiave deve dipendere da tutta la chiave primaria.
#### Nel tuo caso: Se la chiave primaria è composta da "Nome" e "Cognome" (o da un ID unico), e l'età e la data di nascita dipendono da entrambi, allora la tabella è in 2FN.

#### 3 FN?
#### Condizione: La tabella deve essere in 2FN e non ci devono essere dipendenze funzionali transitive.
#### Nel tuo caso: L'età è calcolabile dalla data di nascita. Se la data di nascita è parte della chiave primaria, allora la tabella non è in 3FN, poiché l'età dipende transitivamente dalla chiave primaria attraverso la data di nascita.