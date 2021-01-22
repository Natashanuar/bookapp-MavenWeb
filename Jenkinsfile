pipeline{
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
    
    /*stage {
      stage ('Check-Git-Secrets') {
        sh 'docker pull gesellix/trufflehog
        sh docker run -t gesellix/trufflehog --json > trufflehog
      }
    }*/
    
    stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
     }
    }
    
   /* stage ('Software Composition Analysis') {
      steps {
         sh 'rm -r dependency-check* || true' 
         sh 'wget https://github.com/jeremylong/DependencyCheck/releases/download/v6.0.3/dependency-check-6.0.3-release.zip'
         sh 'unzip dependency-check-6.0.3-release.zip'
         sh './dependency-check/bin/dependency-check.sh --scan ./* --enableRetired -f "ALL" '
       }
    }*/
    
    stage ('Build Execute Jar') {
      steps {
        sh 'mvn clean package'
         }
       }
    
    
  }
}
