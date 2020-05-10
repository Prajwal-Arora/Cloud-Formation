# Cloud-Formation
Deploying a webapp using cloud-formation scripts with AWS 
<p>
Infrastructure-as-code (IAC) that automates the process of creating a secured and high-availability environment and deploying an application packaged and staged in AWS S3 Storage into a Apache Web Server. The script contains all the configurations needed for a repeatable process so that the infrastructure can be discarded and recreated at will multiple times.

<br>

### Detailed Infrastructure Architecture

https://github.com/Prajwal-Arora/Cloud-Formation/blob/master/architecture.jpeg

<br>

### Steps

`1.`  Clone the git repository

`2.`  There are two components to standing up our environment in AWS: `network` and `server`.  Network are the VPCs, gateways, subnets, and routing.  Server are the compute resources, load-balancers, and auto-scaling.

<p>

Network must be setup first. Run the command below with an arbitrary stack name!

```
./aws-stack.sh <stack name> network.yml network-params.json
```
<p>

Once above stack has been created (by checking AWS CloudFormation for stack status), run the command below!

```
./aws-stack.sh <stack name> server.yml server-params.json
```
<br>

> `aws-stack.sh` is a custom shell script and wrapper around `aws cloudformation` cli commands. It includes template validation, checks if stack already exist, and if it does, performs an `update-stack` otherwise `create-stack`.


`3.`  To Check status of the stacks navigate to `CloudFormation` in AWS console

<p>
  
`4.`  To Delete the stack you have created, run the command below!

```
./destroy.sh <stack name given at the time of creation>
```

<br>
