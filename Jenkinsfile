def files = ""
pipeline {
  agent any

  stages {
      stage('Build') {
          steps {
            git branch: 'release',
               url: 'https://github.com/hsawstest/jenkinsdemo.git'
            script{
               // files = sh '$(git diff --name-only $(git merge-base master release))'
               echo "Hi"
            }
         }  
      }
      stage('Deploy') {
          steps {
             sshagent(['stg_key']) {
                  sh "ssh -o StrictHostKeyChecking=no -l ec2-user ip-172-31-41-206.ap-south-1.compute.internal 'whoami'"
                  script{
                     sh "scp Jenkinsfile ec2-user@ip-172-31-41-206.ap-south-1.compute.internal:/home/ec2-user/"
               }
             }
         }
      }
   }
}