EPO PATSTAT Global - 2019 Autumn Edition installation bash scripts for PostgreSQL


These scripts help to insert data into PATSTAT DB from zip files found in PATSTAT bulk data sets, which can be found at [PATSTAT Homepage at EPO.org](https://www.epo.org/searching-for-patents/business/patstat.html#tab-1)and [Link to Downloadpage for registered user](https://publication.epo.org/raw-data/product-list).

First, all zip files should be copied into a folder, preferably in an external hard disk or a HD other than the one containing the PATSTAT DB.

The database PATSTAT should be created in PostgreSQL. To avoid retyping your password export your password to PGPASSWORD and then start the script. 

        $ export PGPASSWORD='_your_password_'

Then run insert_data_patstat.sh, after few hours to control the number of rows in the patstat database run count_rows_in_patstat.sh


