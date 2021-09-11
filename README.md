# AWS CloudFormation Template Example

### 1. Node Application on EC2 Instance

### 2. MySQL Engine of RDS Instance

### 3. Object Store on S3 

### 4. AWS::CloudFormation::Init Metadata Configuration on aws-cfn-bootstrap
#### 1. packages: yum install
#### 2. sources: tarball download from github's repository
#### 3. files
1. redhat SysV init scripts
2. app.env: application configurations(profiling, service port, etc...)
3. db.env: mysql connection credential & Sequelize ORM Configuration
4. store.env: S3 Configuration
#### 4. commands: npm install
#### 5. services: sysvinit enable and start

### 5. Deployment: Creating Stack
```bash
$ aws cloudformation create-stack --stack-name myapp --template-body https://raw.githubusercontent.com/aws-bitacademy/aws-practices/main/03/ch07/ex01.json --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=KeyName,ParameterValue={my-key} ParameterKey=ServicePort,ParameterValue=8080 ParameterKey=DBName,ParameterValue=myapp ParameterKey=DBUserName,ParameterValue=myapp ParameterKey=DBUserPassword,ParameterValue=myapp12345 ParameterKey=BucketName,ParameterValue={my-bucket}
```