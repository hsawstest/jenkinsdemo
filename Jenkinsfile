pipeline {
  agent any

  stages {
      // stage('Build') {
      //     steps {
      //        sshagent(['stg_key']) {
      //            sh "ssh -o StrictHostKeyChecking=no -l ec2-user ip-172-31-41-206.ap-south-1.compute.internal 'whoami'"
      //        }
      //    }
      // }
      stage('Deploy') {
          steps {
             sshagent(['stg_key']) {
                 sh "ssh -o StrictHostKeyChecking=no -l ec2-user ip-172-31-41-206.ap-south-1.compute.internal 'whoami'"
                 sh "scp * ec2-user@ip-172-31-41-206.ap-south-1.compute.internal:/home/ec2-user/"
             }
             
         }
      }
   }
}