# Mercury

Il progetto ha i seguenti componenti:

- [Mercury Timeseries Ingestor]()
- [Mercury Trading Bot]()
- [Mercury UI]()
- [Mercury API]()
- [Mercury API Gateway]()
- [Mercury ML Core]()
- [Mercury Wallet Integration]()
- [Mercury Big Data]()
- [Mercury Fake Data Generator]()
- [Mercury Data Analysis](https://github.com/FedericoSerini/mercury_data_analysis)
- [Mercury Sentiment Analysis Engine]()
### Architettura

L'architettura proposta nella fase 1 prevede 6 strati:

- Ingestion: Tutto quello che riguarda la costruzione della base dati su cui si appoggia la piattaforma, nello stato iniziale si sfrutteranno i web socket messi a disposizione da Binance per quanto riguarda le timeseries di trading. Il tutto verrà caricato sulla base dati Cassandra mediante il message broker kafka che in questo caso svolgerà esclusivamente la funzione di motore di ingestione dati.
- Business Core: Lo strato effettivo su cui punta la piattaforma, ovvero trading basato su ML mediante modelli addestrati da altri strati.
- Application: Tutto quello che riguarda interfacce visive, API ecc..
- Data Analisys And Processing: Strato fondamentale che svolge la funzione di collante tra tutti gli strati, infatti questo strato si occupa di analisi e aggregazione dati
- ML: Questo strato si occupa di generare modelli ML a partire dai dati elaborati e dall'analisi del sentimento (mediante API twitter)
- Integration: Integrazione dei vari wallet su più blockchain

![Archv1](./Archv1.png)


### Tech stack

Linguaggi: Java, Go, Python, Javascript (Node.js)

Database: Cassandra

Caching: Redis

Data Ingestion/Pub Sub: Kafka 

Workflow management: Airflow

Big Data: Spark

Container: Docker

CI/CD: Jenkins

IAM: Keycloak

Versionamento: GitHub

