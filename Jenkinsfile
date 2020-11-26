pipeline {
  agent any
stages {  
  stage('install git'){
            try{
                sh"sudo yum install git -y"
                }
            catch(err)
                {
                    sh"echo error"
                }
            }
  stage('code commit')
   {
        sh 'https://github.com/beadala/usecase2.git'
        }
stage('Test') {
steps {
sh '/usr/local/bin/cfn-lint ./2-tier-Arch.json'
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
