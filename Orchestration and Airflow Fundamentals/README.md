Overview
Hi! I created this project using astro dev init with the Astronomer CLI. This README explains what's in the project and how I run Apache Airflow locally.

Project Structure
dags/: Contains my Airflow DAGs. It includes an example DAG, example_astronauts, which pulls astronaut data from the Open Notify API using the TaskFlow API and dynamic task mapping.

Dockerfile: Defines the Astro Runtime image. I update this if I need to customize the container.

include/: For any extra files I want to add. Currently empty.

packages.txt: For OS-level packages. Empty by default.

requirements.txt: For Python dependencies.

plugins/: Where I can add custom or community plugins.

airflow_settings.yaml: Lets me define Airflow Connections, Variables, and Pools locally.

Running Locally
I start Airflow with:

**astro dev start** #SQL

This launches five Docker containers (Postgres, Scheduler, DAG Processor, API Server, Triggerer). Once ready, the Airflow UI opens at http://localhost:8080, and the Postgres DB is available at localhost:5432/postgres (user/password: postgres).

If ports are taken, I stop existing containers or change the port.

Deploying to Astronomer
If you’re using Astronomer, pushing code to a deployment is easy. Just follow the official deployment docs.
