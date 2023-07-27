
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
      container('kubectl') {  
          sh "kubectl --version"
       }    
      }
    }
    stage('Build docker image') {
      steps {
        container('dockercontainer') {
           
          sh '''
          
       docker run --name kubectl bitnami/kubectl:latest
          
          '''
          
        }
      }
    }
  }
}
