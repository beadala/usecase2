 pipeline {
    agent any
      stages{
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
        try{
            sh 'git clone https://github.com/beadala/usecase2.git'
        }
        catch(err){
            sh(" echo Error cloning Git bucket")
        }
        }
        stage('Validate') {
            steps{
                    sh '/usr/local/bin/cfn-lint ./2-tier-Arch.json'
            }
        }
        stage('Dev') {
            steps{   
                    sh"/usr/bin/aws cloudformation create-stack --stack-name bha-dev --template-body file://2-tier-Arch.json --parameters file://Param2tierArch.json --region 'ap-southeast-2'"        
         }
    }
}
}
