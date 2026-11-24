Entità: Evento
Campo	Tipo	Esempio
id	numero intero	1
titolo	stringa	"Lettere in movimento"
data	data (YYYY-MM-DD)	"2026-06-12"
orario	stringa (HH:MM)	"10:00"
categoria	stringa	"Incontro"
descrizione	stringa	`"Come cambia un messaggio quando cambiano le lettere? Un incontro su tipografia, ritmo e comunicazione visiva."`
immagine	stringa	"assets/lettere-in-movimento.svg"
immagine_alt	stringa	"Lettere geometriche disposte su una griglia"
`sede_id	numero intero	1
Chiave primaria: id, numerico, univoco nell’entità e stabile.

Entità: Sede
Campo	Tipo	Esempio
id	numero intero	1
nome	stringa	"Officina Nord — Sede centrale"
indirizzo	stringa	"Corso Duca degli Abruzzi 24, Torino"
Chiave primaria: id, numerico, univoco nell’entità e stabile.

Relazione
Una sede può ospitare più eventi; ogni evento si svolge in una sede. Evento.sede_id fa riferimento a Sede.id.

Quantità
I dati comprendono sei eventi e tre sedi.

Aggiornamento dei dati
Chi gestisce il sito aggiorna i dati modificando i rispettivi file JSON nella repository, quindi pubblica le modifiche insieme al sito.

Contenuto mostrato dalla pagina
La pagina Programma mostra per ogni evento il titolo, la data, l’orario, la categoria, la descrizione, l’immagine e la sede associata. La pagina Info e luoghi presenta le sedi con i relativi nomi e indirizzi.

erDiagram
    SEDE ||--o{ EVENTO : ospita

    SEDE {
        int id PK
        string nome
        string indirizzo
    }

    EVENTO {
        int id PK
        string titolo
        date data
        string orario
        string categoria
        string descrizione
        string immagine
        string immagine_alt
        int sede_id FK
    }

