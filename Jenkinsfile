pipeline{
  agent any
  stages{
     stage("Maven Build"){
       steps{
            sh "mvn clean package"
        }
    }
    stage("deploy-dev"){
       steps{
          sshagent(['deploy']) {
          sh "scp -rp /home/demo/demo/target/* demo@65.0.127.70:/home/demo"
          }
        }
    }
    }
}
