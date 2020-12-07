# Pact Contract Testing Workshop

https://docs.pact.io/

Demonstrate a provider, consumer and provider verifications set up using a local pact broker to explore how it hangs together

Application code: Kotlin
Test framework: Junit5

The [shop](https://github.com/csbiggar/shop) service (the _consumer_) exposes an inventory api showing the quantity of all biscuit types stocked by the shop. 

It only holds the id of biscuits, so calls the [biscuits](https://github.com/csbiggar/biscuits) service (the _provider_) to find the biscuit name.

The shop service includes a consumer side contract test which, when pushed to the pact broker, will be verified by the [biscuits contract verification tests](https://github.com/csbiggar/biscuits-contract-verifications)


### 1. Set up a local pact broker

Follow the [instructions here](https://github.com/DiUS/pact_broker-docker/blob/master/POSTGRESQL.md) to run a broker locally in docker, connecting to a dockerised posgres database to store your pact data. 

When starting the pact broker, expose it on port `2020` (ie use `-p 2020:80` )

### 2. Publish a consumer contract to the broker

See [shop](https://github.com/csbiggar/shop)

### 3. Ensure the provider service is running

See [biscuits](https://github.com/csbiggar/biscuits) 

### 4. Run the provider verification tests and publish results to broker

See [biscuits contract verification tests](https://github.com/csbiggar/biscuits-contract-verifications)

### 5. Explore the broker to visualise the results

Go to http://localhost/2020





