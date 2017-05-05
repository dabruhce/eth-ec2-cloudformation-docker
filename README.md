# eth-ec2-cloudformation-docker


Region | Launch Template
------------ | -------------
**N. Virginia** (us-east-1) | [![Launch Eth Stack into Virginia with CloudFormation](/images/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=ethereumdockerstack&templateURL=https://s3.amazonaws.com/aws-ethereum-docker-stack/eth.yml)


* input AWS Key for EC2 instance access
* select size

* ensure security group associated with launched EC2 instace is in public subnet, with security groups that allow 22.  default is typically wide openssl

* ssh -i $keyname ec2-user@$EC2_IP
* sudo docker ps

CURL check
* curl -g -X POST -H 'Content-Type: application/json' -H 'Accept: application/json' --data '{"jsonrpc":"2.0","method":"eth_syncing","params":[],"id":1}' $EC2_IP:8545
