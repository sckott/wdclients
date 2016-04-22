
# Package Automation

Writing bespoke R clients can be lots of fun, and is often necessary
beacuse two REST APIs are never the same. However, there are some ways
to automate package creation.

## API Specifications

Some REST APIs have machine readable specifications for their API. Most
small operations don't have time for this, so you usually see this in larger
companies. These specifications allow a definition of the API, but can
also be used to programmatically create a client.

The `apispecs` repo [https://github.com/ropenscilabs/apispecs](https://github.com/ropenscilabs/apispecs)
holds an increasing set of API specifications targeting smaller scientifically
useful APIs that don't already have specifications. We are using the OpenAPI
specification.

xxx...

## Package generator

`apipkgen` [https://github.com/ropenscilabs/apipkgen](https://github.com/ropenscilabs/apipkgen)
is a package that can be used to generate R clients from API specs.

## Keeping up to date
