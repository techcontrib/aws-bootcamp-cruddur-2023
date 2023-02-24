# Week 0 — Billing and Architecture

## Iron Triangle & Agile Triangle - scratching the surface

Iron Triangle is a decision-making philosophy however "traditional" and hence world is shifting towards Agile Triangle where, iron triangle emphasizes cost, scope, and schedule, the agile triangle takes a broader focus on quality (intrinsic quality), value (extrinsic quality), and constraints (cost, scope, and schedule).   In agile triangle methodology, constraints are still a factor in measuring the success of a project, they are not the defining goal.

Traditional iron triangle illustrate as :point_down:

![image](https://user-images.githubusercontent.com/54937605/221245031-a1ce9761-c813-412b-9883-a98aab44c486.png)

And agile triangle looks like this :point_down:

![image](https://user-images.githubusercontent.com/54937605/221245312-46e04e4c-1850-4e2c-ab9a-140abc2b06f3.png)

## Architecting the architecture - quick overview

__Pro-tip: Don't afraid of asking "dump questions" as everyone from different background have different conceptions so be the "dummy in the corner guy" and have a gut asking dump questions.__

It is always seen in a practice that people prefer or end up using a combination of various architecture frameworks _(TOGAF, Zachman Framework, Department of Defense Architecture Framework (DODAF), Federal Enterprise Architecture Framework (FEAF)_ during the design phase. 

![image](https://user-images.githubusercontent.com/54937605/221245937-bc68234d-af29-40f8-9c0e-bd716bd584b8.png)

## Installing and Configuring the AWS CLI on gitpod

Define following task under ".gitpod.yml" file

```tasks:
  - name: aws-cli
    env:
      AWS_CLI_AUTO_PROMPT: on-partial
    init: |
      cd /workspace
      curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
      unzip awscliv2.zip
      sudo ./aws/install
      cd $THEIA_WORKSPACE_ROOT
```

Set the environment variables for AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY & AWS_DEFAULT_REGION.

```gitpod /workspace/aws-bootcamp-cruddur-2023 (main) $ export AWS_ACCESS_KEY_ID="**********"
gitpod /workspace/aws-bootcamp-cruddur-2023 (main) $ export AWS_SECRET_ACCESS_KEY="**************************"
gitpod /workspace/aws-bootcamp-cruddur-2023 (main) $ export AWS_DEFAULT_REGION="us-east-1"
```
And to make these environment variables permanent, execute following commands

```gitpod /workspace/aws-bootcamp-cruddur-2023 (main) $ gp env AWS_ACCESS_KEY_ID="**********"
gitpod /workspace/aws-bootcamp-cruddur-2023 (main) $ gp env AWS_SECRET_ACCESS_KEY="**************************"
gitpod /workspace/aws-bootcamp-cruddur-2023 (main) $ gp env AWS_DEFAULT_REGION="us-east-1"
```

These variables can be seen at :

![image](https://user-images.githubusercontent.com/54937605/221248273-4fc8f3a9-0370-4639-8c45-8774d4fdae4c.png)

Let's commit the changes,

![image](https://user-images.githubusercontent.com/54937605/221248474-12a43f18-2c76-4571-be46-4657e752d1b6.png)

Let's create a new gitpod session and see if AWS CLI is working well :bowing_man:

![image](https://user-images.githubusercontent.com/54937605/221249119-1f87c066-f957-4e93-b55e-c8277b336db1.png)

Opened a new gitpod session, as soon as session launched - gitpod task under .gitpod.yml executed and installed AWS CLI and variables are picked up from environment variables..

```  inflating: aws/dist/cryptography-3.3.2.dist-info/top_level.txt  
  inflating: aws/dist/cryptography-3.3.2.dist-info/AUTHORS.rst  
  inflating: aws/dist/cryptography-3.3.2.dist-info/LICENSE  
  inflating: aws/dist/cryptography-3.3.2.dist-info/LICENSE.APACHE  
  inflating: aws/dist/cryptography-3.3.2.dist-info/INSTALLER  
You can now run: /usr/local/bin/aws --version
gitpod /workspace/aws-bootcamp-cruddur-2023 (main) $ aws --version
aws-cli/2.10.1 Python/3.9.11 Linux/5.15.0-47-generic exe/x86_64.ubuntu.20 prompt/off
gitpod /workspace/aws-bootcamp-cruddur-2023 (main) $ aws sts get-caller-identity
{
    "UserId": "*******************",
    "Account": "*********",
    "Arn": "arn:aws:iam::*************:user/nileshjosh"
}
```

Awesome .. it's working as expected! 