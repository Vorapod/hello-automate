# Docker Network 101

## Via Docker Compose

```sh
docker-compose up
```





## Install go-junit-report

``` sh
go get -u github.com/jstemmer/go-junit-report
```

## Steps
- Run unit test & report
    ``` sh
    # cd hellowrold
    go mod download
    go test -v 2>&1 | go-junit-report > report.xml
    ```
- Build Package (Image)
- Start application
    ```sh
    # cd ..
    docker-compose up -d --build --force-recreate
    ```
- Run API test 
    ```sh
    # cd test/api
    robot greeting.robot
    ```

- Stop application
    ```sh
    # cd ../..
    docker-compose down
    ```


Jenkin
export JENKINS_HOME=`pwd`/jenkinshome
java -jar jenkin.war