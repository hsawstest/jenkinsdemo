pipeline {
  agent any

  stages {
      stage('Build') {
          steps {
            sh 'files=$(git diff --name-only $(git merge-base master release))'
         }  
      }
      stage('Deploy') {
          steps {
             sshagent(['stg_key']) {
                 sh "ssh -o StrictHostKeyChecking=no -l ec2-user ip-172-31-41-206.ap-south-1.compute.internal 'whoami'"
                 sh "scp $files ec2-user@ip-172-31-41-206.ap-south-1.compute.internal:/home/ec2-user/"
             }
             
         }
      }
   }
}