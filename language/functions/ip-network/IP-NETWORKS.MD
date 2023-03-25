# IP NETWORKS FUNCTIONS

---
| Function     | Description                                                 | Input Example                   | Output Example      |
|--------------|-------------------------------------------------------------|---------------------------------|---------------------|
| cidrhost     | Returns the IP address of the Nth host in a CIDR block        | cidrhost("10.0.0.0/24", 3)       | 10.0.0.3            |
| cidrnetmask  | Returns the netmask of a CIDR block                          | cidrnetmask(26)                 | 255.255.255.192     |
| cidrsubnet   | Returns a subnet ID within a larger CIDR block               | cidrsubnet("10.0.0.0/8", 4, 2)  | 10.16.0.0/20        |
| cidrsubnets  | Returns a list of subnets within a larger CIDR block         | cidrsubnets("10.0.0.0/16", 24)  | [10.0.0.0/24, ...]  |
