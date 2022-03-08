# SQL Playground with IBM DB2

## Create Database

1. Start IBM DB2 server locally.  
Run:  
`docker-compose -f db2.yml up -d`  
(or without `-d` to see the logs)
2. Start DBeaver, and run the DDL script to create the schema.

## Run with SchemaCrawler

1. To use SchemaCrawler, run with this command instead.  
`docker-compose -f schemacrawler.yml -f db2.yml up -d`
2. Create the schema in DBeaver.
3. Generate a schema diagram with:  
`docker exec -it schemacrawler /opt/schemacrawler/bin/schemacrawler.sh --server db2 --host db2 --database JAMESTST --schemas JAMESTST --user jamestst --password james123 --info-level standard --command schema --portable-names --output-file share/jamestst.png`
