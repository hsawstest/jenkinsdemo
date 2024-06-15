pipeline {
  agent any

  stages {
      stage('Deploy') {
          steps {

             sshagent(['stg_key']) {
                 // some block
                 sh "ssh -o StrictHostKeyChecking=no -l Linux ip-172-31-41-206.ap-south-1.compute.internal 'whoami'"
                //  sh "ssh -o StrictHostKeyChecking=no -l ubuntu <remote_ip> 'sudo apt update  && sudo apt install -y docker.io'"
                //  sh "ssh -o StrictHostKeyChecking=no -l ubuntu <remote_ip> 'sudo usermod -aG docker ubuntu'"
                //  sh "ssh -o StrictHostKeyChecking=no -l ubuntu <remote_ip> 'source .bashrc'"
                //  sh "ssh -o StrictHostKeyChecking=no -l ubuntu <remote_ip> 'docker run -d -nginx'"
             }
         }
      }
   }
}