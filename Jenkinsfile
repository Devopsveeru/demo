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
            sh "chmod 777 /home/ec2-user/.jenkins -R"
            // sh "cp -rp /home/test/.jenkins/workspace/Demo-pipeline/target/*.jar  /home/test/output"
            sh "scp -rp /home/ec2-user/output/*.jar ec2-user@3.110.148.73:/home/test"
          }
        }
     }
   }
}
