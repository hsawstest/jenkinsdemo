pipeline {
  agent any

  stages {
      stage('Build') {
          steps {
             sh "files=$(git diff-tree --no-commit-id --name-only -r $CI_COMMIT_SHA)"
         }
      }
      stage('Deploy') {
          steps {
             sshagent(['stg_key']) {
                 sh "ssh -o StrictHostKeyChecking=no -l ec2-user ip-172-31-41-206.ap-south-1.compute.internal 'whoami'"
                 sh "scp test.sh ec2-user@ip-172-31-41-206.ap-south-1.compute.internal:/home/ec2-user/"
             }
             
         }
      }
   }
}