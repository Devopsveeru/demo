pipeline{
  agent any
  stages{
     stage("Maven Build"){
       steps{
            sh "mvn clean package"
        }
    }
    stage("deploy-Apache"){
       steps{
          sshagent(['65.0.127.70']) {
          sh ""
          scp -o StrictHostKeyChecking=no target/demo.jar  
            ""
          }
        }
    }
    }
}
