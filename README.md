# DB_exam

## Set-up and data collection
Since the data we're working with is too large to put on GitHub, replicating our project requires some additional steps.
1. Create a folder called 'Data' in the root of the project folder
2. Visit [Datasets IMDB](https://datasets.imdbws.com/) and download all files. Add those files to the 'Data' folder.
3. Visit [Kaggle IMDB reviews](https://www.kaggle.com/datasets/rmisra/imdb-spoiler-dataset?select=IMDB_reviews.json) and download all the files. Add thos to the 'Data' folder as well.

## Setup MSSQL database

Download this file from DB_export folder: [db_exam-final_mssql.bacpac](https://github.com/Gruppe-H/DB_Exam/blob/main/DB_export/db_exam-final_mssql.bacpac)

Click the "download raw file" button to download.

## Setup Neo4j database

The database is called *DB_exam* and the password should fit the one in the frontend .env file.

Download all the files from the "neo4j" folder: [Files for Neo4j setup](https://github.com/Gruppe-H/DB_Exam/blob/main/DB_export/neo4j/)

**Click on Graph DSBM and click plugins and install APOC:** 

<img width="431" alt="image" src="https://github.com/Gruppe-H/DB_Exam/assets/70536109/ceaf9275-874e-41de-b665-99668374b0fb">

**Click here and open the plugins folder and add the downloaded extended.jar file:**

<img width="625" alt="image" src="https://github.com/Gruppe-H/DB_Exam/assets/70536109/4416fab7-ce92-4417-976c-36dd72fa9fda">

**Click here and open config folder:**

<img width="489" alt="Skærmbillede 2024-06-01 kl  15 28 31" src="https://github.com/Gruppe-H/DB_Exam/assets/70536109/9eb0f164-d478-476f-b67a-b83f866b59d1">

* Input the apoc.conf file in the conf folder.

**Click then the import folder:**

<img width="490" alt="image" src="https://github.com/Gruppe-H/DB_Exam/assets/70536109/4e00b4e9-8bcd-4cf1-91f4-124b1eebe6ed">

* And add the *all.cypher* file in here.

**Open settings and add this line:**

<img width="622" alt="image" src="https://github.com/Gruppe-H/DB_Exam/assets/70536109/86b08d63-f99b-439a-807c-c805bc5d3b5c">

* first press *command + F* on mac or *control + F* on windoews to search for the line.

``` dbms.security.procedures.unrestricted=jwt.security.*,apoc.* ```

**Turn the Graph DBMS on and go to the browser and write this command:**

```CALL apoc.cypher.runFile("file:///all.cypher")```

* It will take a while for the file to be done (upto 5-6 hours)
  

## Setup MongoDB

Create a database called "db_exam" and add a collection called reviews and extra_titles:

Review and extra_titles JSON files : [Google docs link](https://drive.google.com/drive/folders/13buYeqK6Vr_sVb3T8aQ6wGuJknSOw5gL?usp=sharing)
