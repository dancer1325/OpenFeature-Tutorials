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
* Check the file '/scripts/flags.flagd.json'
  * 'welcome-message' matches with the feature flag key checked in the code
  * '.variants.entries' check the possibilities
  * '.state' checks if the feature flag is active or not
* `docker run -p 8013:8013 -v $(pwd)/:/etc/flagd/ -it ghcr.io/open-feature/flagd:latest start --uri file:/etc/flagd/flags.flagd.json`
  * Problems:
    * Problem1: "docker: invalid reference format: repository name must be lowercase"
      * Attempt1: `docker run --rm -it --name flagd -p 8013:8013 -v /Users/ADP0253/Documents/Projects/OpenFeature-five-minutes-to-feature-flags/Java SDK + Spring BOOT/demo/scripts/:/etc/flagd/  ghcr.io/open-feature/flagd:latest start --uri file:/etc/flagd/flags.flagd.json`
      * Attempt2: `docker run --rm -it --name flagd -p 8013:8013 -v open:/etc/flagd/  ghcr.io/open-feature/flagd:latest start --uri file:/etc/flagd/flags.flagd.json`
      * Solution: Rename the folder!!! NOT valid folders with special characters as '+'

## Notes
* 'OpenFeatureAPI.class'
  * := main access point to OpenFeature SDK
  * -- designed to act as -- singleton
