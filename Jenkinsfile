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
          sh """
          scp -o StrictHostKeyChecking=no target/demo.war  
          demo@65.0.127.70:/opt/tomcat/webapps/
          ssh demo@65.0.127.70 /opt/tomcat/bin/shutdown.sh
          ssh demo@65.0.127.70 /opt/tomcat/bin/startup.sh
           """
          }
        }
    }
    }
}
