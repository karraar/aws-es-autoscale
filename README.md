# aws-es-auto-scale
A script to auto scale an AWS ElasticSearch cluster based on storage usage (perhaps more later)

```bash
Usage: ./aws-es-auto-scale.py[OPTIONS] --domain-name <es-domain-name>
    -d, --domain-name=<es-domain-name>      ## The AWS ElasticSearch Domain Name to use.
        --min-slaves=<min-slaves-to-use>    ## Optional: The minimum number of slave nodes to use. Default: 5
        --max-slaves=<max-slaves-to-use>    ## Optional: The maximum number of slave nodes to use. Default: 50
    -p, --percent-allow=<%-slaves-to-allow> ## Optional: The % number of slave nodes to allow for growth and sharding. Default: .30
    -c, --configure                         ## Optional: Actually request cluster configuration changes.  Default false
```

## Example output with no execute.
```bash
./aws-es-auto-scale.py --d my-stage

Using the following configuration:
DomainName:    my-staging
min-slaves:    5
max-slaves:    50
percent-allow: 0.3
configure:     False

Cluster Nodes: 8 (3 Masters and 5 Slaves).
Cluster Disk Space(GB): 250.00 Total (55.70 Used, 194.30 Available).
Cluster Slave Nodes: Currently using: 5, Need: 2, with allowance: 3, with safeguard: 5.
````
