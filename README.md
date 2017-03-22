# Dockering PEcAn
To fully Dockerize PEcAn, I am thinking of following this strategy:
1. Creating customized Dockerfile(s) for the different components (databases, gui, models).
2. Using the above image(s) in a docker-compose file, also using official images (Postgres).
3.  Trying everything out as a Kubernetes cluster.

#Usage Example

Implemetning as a docker-compose.yml file.

A docker-compose.yml example
```Bash
pecan-gui:
 image: pecan-gui
 volumes:
  - <PWD>:/
 links:
  - mysql:db
  environment:
  - any environment variable
  restart: always

pecan-cmd:
  image: pecan-cmd
  volumes:
  - <PWD>:/
  environment:
  - Any variables
  restart: always
  .
  .
  .
 ```

			       with this, we can setup reactome.
