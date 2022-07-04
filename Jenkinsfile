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
            sh "chmod 777 /home/demo/.jenkins -R"
          sh "scp -rp /home/demo/.jenkins/workspace/test_project/target/*.jar demo@65.0.127.70:/home/demo"
          }
        }
    }
    }
}
