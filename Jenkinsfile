pipeline {
  agent {
    kubernetes {
      yamlFile 'demo.yaml'
      idleMinutes 1
    }
  }
  stages {
    stage('kubernetes deploy') {
      steps {
      container('mavencontainer') {  
          sh "mvn --version"
       }    
      }
    }
    stage('Build docker image') {
      steps {
        container('docker') {
           
          sh '''
          
       docker build -t supra/nginx:latest .
          
          '''
          
        }
      }
    }
  }
}
