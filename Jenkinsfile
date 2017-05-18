pipeline {
  agent none
  stages {
    stage('build') {
      steps {
        parallel(
          "build": {
            sh 'mvn clean install'
            
          },
          "": {
            echo 'test'
            
          }
        )
      }
    }
  }
  post {
    success {
      archive 'target/blueocean-pipeline-editor.hpi'
      
    }
    
    always {
      junit 'target/**/*.xml'
      
    }
    
  }
}