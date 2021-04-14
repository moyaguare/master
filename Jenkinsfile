pipeline {
  agent any 
  tools {
    maven 'Maven'
  }
  stages {
    stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
           ''' 
      }
    }
      stage ('Build') {
      steps {
      echo 'This is a minimal pipeline.'
        }
    }
    stage ('Deploy-To-Tomcat') {
            steps {
           sshagent(['tomcat']) {
                sh 'scp -o StrictHostKeyChecking=no target/*.war ubuntu@52.15.34.178:/prod/apache-tomcat-8.5.65/webapps/webapp.war'
              }      
           }       
    }
   }
}
