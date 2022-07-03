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
          sh "scp -rp /home/demo/demo/target/* demo@13.126.214.247:/home/demo"
          }
        }
    }
    }
}
