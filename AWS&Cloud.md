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


#### Questions asked
     1. Explain whole flow of request from ur API gateway to you lambda and response back.
     2. Is SNS and SQS lifo or fifo.
     3. How do u ensure your api calls are not being exposed to outside world?
