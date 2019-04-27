# AuthService

This application was generated using Coolybot 5.8.2, you can find documentation and help at [https://www.coolybot.tech/documentation-archive/v5.8.2](https://www.coolybot.tech/documentation-archive/v5.8.2).

This is a "uaa" application intended to be part of a microservice architecture, please refer to the [Doing microservices with Coolybot][] page of the documentation for more information.

This is also a Coolybot User Account and Authentication (UAA) Server, refer to [Using UAA for Microservice Security][] for details on how to secure Coolybot microservices with OAuth2.
This application is configured for Service Discovery and Configuration with the Coolybot-Registry. On launch, it will refuse to start if it is not able to connect to the Coolybot-Registry at [http://localhost:8761](http://localhost:8761). For more information, read our documentation on [Service Discovery and Configuration with the Coolybot-Registry][].

## Development

To start your application in the dev profile, simply run:

    ./mvnw

For further instructions on how to develop with Coolybot, have a look at [Using Coolybot in development][].

## Building for production

To optimize the AuthService application for production, run:

    ./mvnw -Pprod clean package

To ensure everything worked, run:

    java -jar target/*.war

Refer to [Using Coolybot in production][] for more details.

## Testing

To launch your application's tests, run:

    ./mvnw clean test

For more information, refer to the [Running tests page][].

### Code quality

Sonar is used to analyse code quality. You can start a local Sonar server (accessible on http://localhost:9001) with:

```
docker-compose -f src/main/docker/sonar.yml up -d
```

Then, run a Sonar analysis:

```
./mvnw -Pprod clean test sonar:sonar
```

For more information, refer to the [Code quality page][].

## Using Docker to simplify development (optional)

You can use Docker to improve your Coolybot development experience. A number of docker-compose configuration are available in the [src/main/docker](src/main/docker) folder to launch required third party services.

For example, to start a mongodb database in a docker container, run:

    docker-compose -f src/main/docker/mongodb.yml up -d

To stop it and remove the container, run:

    docker-compose -f src/main/docker/mongodb.yml down

You can also fully dockerize your application and all the services that it depends on.
To achieve this, first build a docker image of your app by running:

    ./mvnw package -Pprod verify jib:dockerBuild

Then run:

    docker-compose -f src/main/docker/app.yml up -d

For more information refer to [Using Docker and Docker-Compose][], this page also contains information on the docker-compose sub-generator (`coolybot docker-compose`), which is able to generate docker configurations for one or several Coolybot applications.

## Continuous Integration (optional)

To configure CI for your project, run the ci-cd sub-generator (`coolybot ci-cd`), this will let you generate configuration files for a number of Continuous Integration systems. Consult the [Setting up Continuous Integration][] page for more information.

[coolybot homepage and latest documentation]: https://www.coolybot.tech
[coolybot 5.8.2 archive]: https://www.coolybot.tech/documentation-archive/v5.8.2
[doing microservices with coolybot]: https://www.coolybot.tech/documentation-archive/v5.8.2/microservices-architecture/

[Using UAA for Microservice Security]: https://www.coolybot.tech/documentation-archive/v5.8.2/using-uaa/[Using Coolybot in development]: https://www.coolybot.tech/documentation-archive/v5.8.2/development/
[Service Discovery and Configuration with the Coolybot-Registry]: https://www.coolybot.tech/documentation-archive/v5.8.2/microservices-architecture/#coolybot-registry
[Using Docker and Docker-Compose]: https://www.coolybot.tech/documentation-archive/v5.8.2/docker-compose
[Using Coolybot in production]: https://www.coolybot.tech/documentation-archive/v5.8.2/production/
[Running tests page]: https://www.coolybot.tech/documentation-archive/v5.8.2/running-tests/
[Code quality page]: https://www.coolybot.tech/documentation-archive/v5.8.2/code-quality/
[Setting up Continuous Integration]: https://www.coolybot.tech/documentation-archive/v5.8.2/setting-up-ci/
