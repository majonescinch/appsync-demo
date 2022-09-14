# AppSync Demo

Building GraphQL APIs using AppSync.

## DynamoDB

https://docs.aws.amazon.com/appsync/latest/devguide/tutorial-dynamodb-resolvers.html
https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-dynamodb.html

Example request:

```graphql
query VehicleDataQuery {
    vehicleData(vin: "WI0KWXWQCKFD87923") {
        make
        model
    }
}
```

## HTTP

https://docs.aws.amazon.com/appsync/latest/devguide/tutorial-http-resolvers.html
https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-http.html

Example request:

```graphql
query VehicleQuery {
  vehicleData(filter: {vin: "WI0KWXWQCKFD87923", type: "METAL", snapshotVersion: "1"}) {
    header {
      type
      vin
    }
    profileId
    snapshotVersion
    packs {
      catalogue_basic {
        fuelType
        version
      }
    }
  }
}
```

## OpenSearch

https://docs.aws.amazon.com/appsync/latest/devguide/tutorial-elasticsearch-resolvers.html
https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-elasticsearch.html

Example request:

```graphql
query SearchQuery {
  vehicles(pageNumber: 0, pageSize: 10) {
    vehicleListings {
      bodyType
      colour
    }
  }
}
```