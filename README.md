# airflow_set_up
## step1
Fetch the docker-compose.yml file using the code below
```
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.10.0/docker-compose.yaml'
```
Create the following directories using this command
```
mkdir -p ./dags ./logs ./plugins ./config
echo -e "AIRFLOW_UID=$(id -u)" > .env
```
create a .env file and set-up the airflow user
```
echo -e "AIRFLOW_UID=$(id -u)" > .env
```
Initialize the database and set the first user account 
```
docker compose up airflow-init
```
## Running Airflow
You can start all services by running
```
docker-compose up
```

