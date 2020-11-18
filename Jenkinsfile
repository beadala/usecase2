pipeline {
  agent {label "master"}
stages {  
stage('Test') {
steps {
sh '/usr/local/bin/cfn-lint ./*.json'
}
}
stage('Deploy') {
steps {
sh 'cd /usr/local/bin/'
sh 'ls'
sh "/usr/local/bin/aws cloudformation create-stack --stack-name twotire --template-body file://Param2tierArch.json --region 'ap-southeast-2'"
}
}
}
}