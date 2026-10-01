# Muli IP Workarround with Helm Templates

For the full workarround with post vm migration patch instructions for adding
the Primary UDN See: https://github.com/mathianasj/udn-two-ip-workaround

This project is a pass at wiring everything as a Helm Template to make the
process of migrating a large collection of VMs manageable.

Variables files are expected to have a `tenants` variable which holds an array of tenants.
Tenants may be separated into separate variables files or lumped together in one file.

## Run
```shell

# dump output to stdout
helm template . -f tenants.yaml

# pipe output to oc
helm template . -f tenants.yaml | oc apply -f -

# generate output as individual yaml files for simpler debuging / validation
helm template . -f tenants.yaml --output-dir generated
ls -l generated/multi-ip-workaround/templates/

```

![Alt text](multiple-ip-workarround.svg)


