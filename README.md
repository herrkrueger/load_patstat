EPO PATSTAT Global - 2019 Autumn Edition installation bash scripts for PostgreSQL


These scripts help to insert data into PATSTAT DB from zip files found in PATSTAT bulk data sets, which can be found at [PATSTAT Homepage at EPO.org](https://www.epo.org/searching-for-patents/business/patstat.html#tab-1)and [Link to Downloadpage for registered user](https://publication.epo.org/raw-data/product-list).

1. All zip files should be copied into a folder. You will be prompted for the location of this folder. 

2. Created the database patstat with pgAdmin in PostgreSQL.

3. Export your password to avoid retyping it with e.g.

        $ export PGPASSWORD='_your_password_'

4. run the script ./insert_data_to_patstat.sh

The script creates the PATSTAT Tables acccording to 'create_patstat_tables'. Pleasse check, if the database structure got changed, if you are using the script to import another version as the Autumn 2019 edition. 

ATTENTION: There will be no import of "tls203_appl_abstr". Please add it to the script manually if you need the 100GB of abstract data in addition to the e.g. tls202_appln_title in your PATSTAT.

The script then unzips the files in a tmp directory and imports them with psql into your database. This takes some time, depending on your hd speed while unzipping and your internet connection and server performance (took me 2h:40m) 

To create the keys later, check the "create_patstat_keys.sql" and run this command:

        $ psql -h _your_pg_serer -d patstat < ./create_patstat_keys.sql
        
Tbd: Index creation (gin/gist for fulltext search in title or names)
Tbd: Performance tuning
