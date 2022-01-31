[![Java CI](https://github.com/blacar/product/actions/workflows/javaci.yml/badge.svg?branch=actions)](https://github.com/blacar/product/actions/workflows/javaci.yml)

Steps to test this API:
  1.- Clone this repository
  2.- mvn -Pdev clean package
  3.- docker run -e "SPRING_PROFILES_ACTIVE=dev" -p 8080:8080 -t product-api:0.0.1
  4.- go to: http://127.0.0.1:8080/swagger-ui/index.html


Notes:
  db.png is the data model, based on the "Kimbal methodology".
  aws-ebs.yaml is the template to create/update the application.( Not tested within aws )




#clean
mvn -Pdev clean package -DskipTests

#unit test
mvn -Pdev test


#integration test
mvn -Pdev failsafe:integration-test


#run api
docker run -e "SPRING_PROFILES_ACTIVE=dev" -p 8080:8080 -t product-api:0.0.1


#create an db instance
docker run --name my-postgres-bd -e POSTGRES_PASSWORD=12345 -p 5432:5432 -d postgres



