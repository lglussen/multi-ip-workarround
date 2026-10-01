# Muli IP Workarround with Helm Templates

Variables files are expected to have a `customers` variable which holds an array of customers.
Customers may be separated into separate variables files or lumped together in one file.

## Run
```shell

helm template . -f customers.yaml

```

