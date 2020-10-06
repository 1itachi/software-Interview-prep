## AWS

#### lambda
  usual syntax in node.js   exports.handler = async (event, context, callback)
  event=> event is the one which triggers our lambda
  context=> When Lambda runs your function, it passes a context object to the handler.
  This object provides methods and properties that provide information about the invocation, function, and execution environment.

#### How do you ensure that your api calls are not being exposed to outside world?
    One way is to configure the authorizer property of API gateway. Authorizer is nothing but a lambda functions
    which authorizes the incoming request.
    We can also cerate REST Api which is available within a VPC. (Virtual private cloud)

#### What is VPC?
      A virtual private cloud (VPC) is a virtual network dedicated to your AWS account.
      It is logically isolated from other virtual networks in the AWS Cloud.

#### Difference between SQS and SNS?
      Receivers have to poll SQS to receive messages.
      Polling inherently introduces some latency in message delivery in SQS unlike SNS where messages are immediately pushed to subscribers.


#### Route table
     A route table contains a set of rules, called routes, that are used to determine where network traffic from your subnet or gateway is directed.

#### Docker & VM
      VM- individual OS and isolate systems. Hypervisor used.
      Docker- Shared OS and isolate applications. Docker Daemon used.

#### Kubernetes
      Container orchestration - manage docker containers (Docker swarm)
                              - Good Auto scaling (Kubernetes) -supports AWS/GCP/AZURE
      Can run 1000's of instances, upgrade or rollback

#### subnet
        When we create VPC, it spans entire availability zones in the region. We can add one or more subnets in each vpc. Subnet resides entirely in single zone and cannot span zones.

1. How to publsih message from lambda to sns?
=> const params = {
  Message: "abc",
  MessageStructure: 'json',
  TopicARN: SNS_TOPIC_ARN
}      
const publishPromise = sns.publish(params).promise();


2. How to send messages to sqs?
=>   var params = {
    MessageBody: JSON.stringify(event),
    QueueUrl: QUEUE_URL
  };
  sqs.sendMessage(params, function(err,data){});


3. Three basic types of cloud services by aws?
=> compute(lambda, elastic bean stalk) , Storage(s3) , Networking(VPC, Route53)

4. CloudFormation anatomy:
=>


#### Questions asked
     1. Explain whole flow of request from ur API gateway to you lambda and response back.
     2. Is SNS and SQS lifo or fifo.
     3. How do u ensure your api calls are not being exposed to outside world?
