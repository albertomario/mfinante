# Mfinante scraper

Description:
------------

Dockerized application to get data from mfinante.ro about companies.


System prerequisites:
---------------------

1. Install docker (including compose):

  ```
  sudo apt-get install docker-engine
  ```
  

Project installation:
---------------------

1. Create local docker-compose from example:

  ```
  cp docker-compose-example.yml docker-compose.yml
  ```


Run project:
------------

1. Start docker service:

  ```
  sudo service docker start
  ```

2. Start a new container from image:

    ``` 
    docker-compose up
    ```
    
3. Project is up and running at:

    ```
    http://<host>:5000/find?cui=<cui>&year=<year>
    ```

Exposed URLS:
-------------

1. Get raw data - params: cui, year

    ```
    http://<host>:5000/find-raw?cui=<cui>&year=<year>
    ```

2. Get accounting data - params: cui, year
 
    ```
    http://<host>:5000/find?cui=<cui>&year=<year>
    ```
 
 
JSON structure:
---------------

1. Request:
    * cui 
    * year
    * url - url built from params
    
2. Response:
    * success - boolean
    * result - dict containing company data 
    * error - string containing error class if any error occured
    
