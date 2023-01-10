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
    stage ('BuilD') {
      steps {
      sh 'mvn clean package'
    }
    
   }
    
   stage ('Deploy-To-Tomcat'){
		steps {
			sshagent(['tomcat']) {
				sh 'scp -o StrictHostKeyChecking=no target/*.war ubuntu@18.183.216.53:/root/tomcatnew/apache-tomcat-9.0.70/webapps/webapp.war'
				}
			}
}
 }
}

