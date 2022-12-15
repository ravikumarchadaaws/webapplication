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
      sh 'mvn clean package'
    }
    
   }
    stage ('SCA') {
      steps {
      sh 'whoami'
    }
    
   }
    stage ('Nikto Scan') {
      steps {
      sh 'nikto -host 13.115.215.63 -port 8080'
    }
    
   }
 }
}

