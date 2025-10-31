# Db library

Imparare a modellizzare una parte di realtà.

In questo esempio, strutturiamo il databse che modellizza una biblioteca


## Tables:
- books
- loans (prestiti)
- users
- copies
- genres

### Table: Books
- id: INT || BIGINT AI NOTNULL UNIQUE PK INDEX
- isbn: CHAR(13) UNIQUE NOT NULL INDEX
- title: VARCHAR(255) NOT NULL
- author: VARCHAR(150) NOT NULL
- publisher: VARCHAR(50) NOT NULL
- ?genre?
- position: VARCHAR(20) UNIQUE NOT NULL
- ?is_available: TINNYINT NOT NULL
- ?copies?
- year: YEAR NULL
- ?cover_image?
- plot: TEXT NULL
- language: CHAR(5) DEFAULT(it-IT) // it-IT
- series: VARCHAR(20) NULL
- ?end_of_loan?
- note: TEXT NULL
