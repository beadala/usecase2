pipeline {

 
agent any

 
stages{

 
stage('install git'){

 
steps{

 
script{

 
try{

 
sh"sudo yum install git -y"

 
}

 
catch(err)

 
{

 
sh"echo error"

 
}

 
}

 
}

 
}

 
stage('code commit')

 
{

 
steps{

 
script{

 
try {

 
sh 'git clone https://github.com/beadala/usecase2.git'

 
}

 
catch(err) {

 
sh(" echo Error cloning Git bucket")

 
}

 
}

 
}

 
}

 
stage('Validate') {

 
steps{

 
sh '/usr/local/bin/cfn-lint ./2-tier-Arch.json'

 
}

 
}

 
stage('Dev') {

 
steps{

 
sh"/usr/local/bin/aws cloudformation create-stack --stack-name bhtest-dev-1 --template-body file://2-tier-Arch.json --parameters file://Param2tierArch.json --region 'ap-southeast-2'"

 
}

 
}

 
}

 
}
