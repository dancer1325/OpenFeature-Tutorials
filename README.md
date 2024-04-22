<!-- markdownlint-disable MD033 -->
<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/open-feature/community/0e23508c163a6a1ac8c0ced3e4bd78faafe627c7/assets/logo/horizontal/white/openfeature-horizontal-white.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/open-feature/community/0e23508c163a6a1ac8c0ced3e4bd78faafe627c7/assets/logo/horizontal/black/openfeature-horizontal-black.svg">
    <img align="center" alt="OpenFeature Logo">
  </picture>
</p>

<h2 align="center">Five Minutes to Feature Flags Tutorial</h2>

[Documentation Link](https://openfeature.dev/docs/tutorials/five-minutes-to-feature-flags)

# Goal
* Add feature flagging to a Node service -- via express server --

# Ways to run
## 👩‍💻 Interactive Tutorial == browser
* Requirements
  * free Killercoda account
* [Killercoda](https://killercoda.com/open-feature/scenario/five-minutes-to-feature-flags)

## 📚 Written Tutorial == locally
* Requirements
  * NodeJs >= v16.0
* Steps
  * `npm install`
### Basic Express server
* `node 01_vanilla.js`
  * Open in your browser or launch the curl
    * 'http://localhost:3333/' -- Check the "Hello, world!" -- 
### Static flag + cowsay
* [cowsay](https://www.npmjs.com/package/cowsay)
  * `.say(StringToPass)` customize the stringToPass 
* Static flag -- adjust 'withCow' in the code -- 
* `node 02_basic_flags.js`
  * Open in your browser or launch the curl
    * 'http://localhost:3333/' -- Check the "Hello, world!" customized with cow draw --
### OpenFeature
#### Without configuring feature flag provider 
* '@openfeature/server-sdk' added
* `node 03_openfeature.js` 
  * Open in your browser or launch the curl
    * 'http://localhost:3333/' -- Check the "Hello, world!" WITHOUT customized cow draw --
#### With feature flag provider
* OpenFeature is JUST a specification!!!
  * -> you need a Open Feature Flag system / framework
* Possible feature flag providers
  * commercial product
  * open-source offering
  * internal tool
  * simple one without a backend -- this case --
  * ...
* `node 04_openfeature_with_provider.js`
  * Open in your browser or launch the curl
    * 'http://localhost:3333/' -- Check the "Hello, world!" customized with cow draw --
      * if you want to get WITHOUT customizing -> you need to stop & change the 'defaultVariant' in FLAG_CONFIGURATION & start the server again
