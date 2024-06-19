pipeline{
    agent any
        stages{

            stage('checkout'){
                steps{
                    git branch: 'main', credentialsId: 'git-cred', url: 'https://github.com/vinodabadiger/jen-py-dock.git'
                }  
            } 

            stage('build'){
                steps{
                    sh "docker build -t python:2 ." 
                }  
            } 

            
            stage('tag'){
                steps{
                    sh "docker tag python:2 vinoda32/python:2" 
                }  
            }

             
            stage('push'){
                steps{
                    withDockerRegistry(credentialsId: 'docker-cred', url: 'https://index.docker.io/v1/') {
                      sh "docker push vinoda32/python:2" 
                    }  
               }

         }

}
