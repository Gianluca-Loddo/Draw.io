# Db library

Imparare a modellizzare una parte di realtà.

In questo esempio, strutturiamo il databse che modellizza una biblioteca


## Tables:
- books
- loans (prestiti)
- users
- copies
- genres
- conditions

### Table: Books

- id: INT || BIGINT AI NOTNULL UNIQUE PK INDEX
- title: VARCHAR(255) NOT NULL
- author: VARCHAR(150) NOT NULL
- position: VARCHAR(20) UNIQUE NOT NULL
- plot: TEXT NULL
- ?series: VARCHAR(20) NULL
- note: TEXT NULL

### Table: copies

- id
- condition_id FK
<!-- In un database relazionale, l’abbreviazione FK sta per Foreign Key, cioè chiave esterna.
Una Foreign Key (FK) è un vincolo (constraint) che serve a collegare due tabelle tra loro, garantendo la coerenza dei dati.
In pratica, una FK è un campo (o un insieme di campi) che fa riferimento alla chiave primaria (PK) di un’altra tabella.
Es.
TABELLA CLIENTI
| id_cliente (PK) | nome  | città  |
| --------------- | ----- | ------ |
| 1               | Mario | Roma   |
| 2               | Lucia | Milano |
TABELLA ORDINI
| id_ordine (PK) | data       | id_cliente (FK) |
| -------------- | ---------- | --------------- |
| 101            | 2025-10-31 | 1               |
| 102            | 2025-11-01 | 2               |

id_cliente nella tabella Clienti è la Primary Key (PK).

id_cliente nella tabella Ordini è una Foreign Key (FK) che fa riferimento a Clienti(id_cliente). 

IN SINTESI
| Sigla | Nome completo | Significato                                     |
| ----- | ------------- | ----------------------------------------------- |
| PK    | Primary Key   | Identifica univocamente una riga                |
| FK    | Foreign Key   | Collega una riga a un’altra tabella (relazione) |
-->

- isbn: CHAR(13) UNIQUE NOT NULL INDEX
- cover_image:
- publisher: VARCHAR(50) NOT NULL
- year: YEAR NULL
- is_available: TINNYINT NOT NULL
- language: CHAR(5) DEFAULT(it-IT) // it-IT
- note: TEXT NULL

### Table: conditions

- id
- name
- slug (nome senza spazi, tutto minuscolo)

### Table: genres

- id
- name 
- slug

### Pivot Talbe: book_genre
- id
- book_id
- genre_id