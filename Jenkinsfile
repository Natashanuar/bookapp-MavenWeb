pipeline{
/*environment{
    registry = "tasdocker00/sample_devops-master"
    registryCredential = 'docker-hub-credentials'
    dockerImage = ''
    dockerImageLatest = ''
}*/
  agent any
    tools {
      maven 'Maven'
  }
  
  stages {
    stage ('Cloning Git') {
      steps {
        git 'https://github.com/Natashanuar/bookapp-web.git'
     }
    }
    
    stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
     }
    }
    
    stage ('Build Execute Jar') {
      steps {
        sh 'mvn clean package'
         }
        }
} 
}
