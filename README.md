# Spotify Daily songs (ETL)

As part of a free ETL course, I built a data pipeline using Spotify API. The feed runs everyday and downloads data on the songs I've listened to during the day. It then saves the data in a SQLite database on premise (my local machine).

### Extract
The first step in the ETL process is extracting the data. Meaning you download data from a data vendor (e.g. Spotify). The data format in this case is in json format which resembles Python dictionaries. Pandas DataFrame is used in order to structure the data into columns.

### Transform
The next step in the process is to transform the now structured data. The data from the vendor is validated by checking for duplicates, null values, empty files etc. We also identify a row suitable to be a primary key/ unique identifier for each row. This phase utilizes the "garbage in, garbage out" principle. In order to continue to the last phase (loading data into the database) the data must pass all tests.

### Load
In the load stage we load the now validated data into a SQLite database with the help of an Object Relational Mapper (ORM) tool that translates Python classes to tables on relational databases and automatically converts function calls to SQL statements. In this case we use SQLAlchemy.

### Airflow
Would need to use Airflow to automize the ETL process! Will update project soon.
