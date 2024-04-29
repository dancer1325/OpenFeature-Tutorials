# Goal
* integrate OpenFeature Java SDK
* install & configure an OpenFeature provider -- flagd in this case --
* perform basic feature flagging

## Prerequirements
* Java8+
* [Docker](https://docs.docker.com/get-docker/)

## How has it been created?
* [Spring Initializer](https://start.spring.io/) and selecting the archetype 'web'
* Add the dependencies 'dev.openfeature:sdk' & 'dev.openfeature.contrib.providers:flagd'

## How to run locally?
* `mvn clean install`
* `java -jar target/demo-0.0.1-SNAPSHOT.jar`
* Trigger the requests specified in 'sample-request.http', selecting 'localSpringBoot'
  * if you do NOT configure any provider -> you will get always "Hello!"
  * if you configure a provider (next section) -> you will get always "Hello, welcome to this OpenFeature-enabled website!"

## How to configure a provider?
* TODO:

## Notes
* 'OpenFeatureAPI.class'
  * := main access point to OpenFeature SDK
  * -- designed to act as -- singleton
