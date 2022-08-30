pipeline{
  agent any
  stages{
     stage("Maven Build"){
       steps{
            sh "mvn clean package"
        }
    }
    stage("Deploy-Test"){
      steps{
         sshagent(['Deploy']) {
            sh "chmod 777 /home/test/.jenkins -R"
            sh "cp -rp /home/test/.jenkins/workspace/Demo-pipeline/target/*.jar  /home/test/output"
            sh "scp -rp /home/test/output/*.jar sekhar@127.0.0.1:/home/test"
          }
        }
     }
   }
}
