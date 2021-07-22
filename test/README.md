# Testing

Testing is performed using a Docker container. First build the container:
```
docker build --build-arg UID=$(id -u) --build-arg GID=$(id -g) -f test/Dockerfile.debian -t pgaudit-analyze-test .
```
Then run the test. The path for the PostgreSQL version to be tested must be supplied:
```
docker run -v $(pwd):/pgaudit-analyze pgaudit-analyze-test /pgaudit-analyze/test/test.pl --pgsql-bin=/usr/lib/postgresql/13/bin
```
