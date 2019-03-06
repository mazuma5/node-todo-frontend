
pipeline {
  enviroment{
    registry = "mazuma5/pipeline-project"
    registryCredential = 'Dockerhub'
    dockerImage = ''
    containerId = sh(script: 'docker ps -aqf "name=node-app"', returnStdout:true)
  }
  agent any
  tools {nodejs "node"}
    
  stages {
        
    stage('Cloning Git') {
      steps {
        git 'https://github.com/mazuma5/node-todo-frontend'
      }
    }
        
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
     
    stage('Test') {
      steps {
         sh 'npm test'
      }
    }      
  }
}
