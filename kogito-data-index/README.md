# Kogito Data Index Helm Chart
This is a Helm chart to deploy a Kogito application with Kogito data index and PostgreSQL persistence. 

This chart will setup all of the following services:
- Postgresql
- Kafka
- Kogito Data Index
- Kogito Jobs
- Kogito Management Console
- Kogito Task Console
- Keycloak

# Example Usage
By default, this will deploy the Kogito [process-usertasks-quarkus-persistence-with-console](https://github.com/kiegroup/kogito-examples/tree/stable/process-quarkus-example) 
image which I have uploaded onto 
[Quay](https://quay.io/repository/kiegroup/examples-process-quarkus-example). Follow the [initial setup](../README.md#Usage), then run these commands 
in the base directory of the repository:
## OpenShift
```sh
helm install process-data-index kogito/kogito-data-index
export KOGITO_URL=$(kubectl get routes -o jsonpath="{.items[?(@.metadata.name=='process-data-index')].spec.host}")
```