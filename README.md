# installation
Use the code below to safely install apache airflow. This method helps avoid dependancy related problems.
Make sure to repelace the python version with the version you are using for your project
```
AIRFLOW_VERSION=2.8.1
PYTHON_VERSION=3.10
CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"

pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"

```

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
All services can be stoped by running
```
docker-compose down
```
To stop and delete containers, delete volumes with database data and download images, run:
```
docker compose down --volumes --rmi all
```

