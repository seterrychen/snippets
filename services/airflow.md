i# Airflow

## Installation
```
$ pip install apache-airflow
$ pip install apache-airflow[crypto]
```

## Environment setup

### Home path
```
$ mkdir ~/airflow
$ export AIRFLOW_HOME=~/airflow
```

### db
```
$ # initialization
$ airflow initdb
$
$ # reset db
$ airflow resetdb
```

## Start service
```
$ # web server
$ airflow webserver -p 8080
$
$ # scheduler
$ airflow scheduler
```

## Usage case
### Delete all example DAG
```
# vim $AIRFLOW_HOME/airflow.cfg
load_examples = False
# airflow resetdb
# # dont forget stopping scheduler
```

### Create DAG
* put python code under `$AIRFLOW_HOME/dags` folder



## Reference
* [Apache Airflow: Tutorial and Beginners Guide | Polidea](https://www.polidea.com/blog/apache-airflow-tutorial-and-beginners-guide/)
* [🌈Apache Airflow for beginners](https://www.youtube.com/watch?v=YWtfU0MQZ_4)
