# Elastic-Beanstalk-provision

##How to deploy flyimg application to AWS Elastic Beanstalk

In this article we'll see how to deploy flyimg application to AWS Cloud with Elastic Beanstalk.

Please make sure that [`eb cli`](http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) tool is installed.

## Instalation the project

Create the project with `composer create`:

```sh
composer create-project flyimg/flyimg
```

## Eb init

CD into the folder flyimg and run eb init:

```sh
eb init
```

This will init your aws account, it'll ask you to Select a default region and provide your credentials (aws-access-id,aws-secret-key).

After it'll ask about Application Name (default is folder name which is flyimg).

Next eb cli will detect the Dockerfile inside your folder, you'll get this quesiton `It appears you are using Docker. Is this correct?` enter yes and choose the default docker version which is the latest.

Finally, eb cli ask you if you want to set up SSH for your instances, you can choose yes and create a new keypair.

## Creating the environment and deploying the application

If you don't have any environment in your Elastic-Beanstalk application, you can run this command `eb create env-name` and it'll create the env-name environment and proceed with the deployment in the same time, 

```sh
eb create staging
```

After launching this command you'll see the logs of events happening in your EB AWS.


## Visualizing the application

You can open your application dashboard web page directly through this command:

```sh
eb console
```

When clicking in the URL in the top you should see the wekcome phrase from flyimg app: `Hello from Docker!`



Enjoy !
