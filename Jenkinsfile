pipeline {
    agent any
	

 stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/sanjeevsuman007/Devops-Practical.git'
             
          }
        }
       

  stage('Docker Build and Tag') {
           steps {
              
                sh 'docker build -t devops9class:latest .' 
                sh 'docker tag devops9class sanjeevsuman007/devops9class:$BUILD_NUMBER'
               
          }
        }
  stage('Publish image to Docker Hub') {
            steps {
        withDockerRegistry([ credentialsId: "DockerHub", url: "" ]) {
           sh  'docker push sanjeevsuman007/devops9class:$BUILD_NUMBER' 
		}
                  
          }
        }
		
    }
}
