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
                    sh "docker build -t python:3." 
                }  
            } 

            
            stage('tag'){
                steps{
                    sh "docker tag python:3 vinoda32/python:3" 
                }  
            }

             
            stage('push'){
                steps{
                    withDockerRegistry(credentialsId: 'docker-cred', url: 'https://index.docker.io/v1/') {
                      sh 'docker push vinoda32/python:3'
                    }  
               }
            }
        
            stage('ssh'){
                steps{
                    script{
                        sshPublisher(
                            publishers: [
                                sshPublisherDesc(
                                    configName: 'production',
                                    verbose: true ,

                                         transfers: [
                                            sshTransfer(
                                                  execCommand: 'docker images', 
                                                  execTimeout: 120000, 
                                            )
                                        ], 
                                      usePromotionTimestamp: false, 
                                      useWorkspaceInPromotion: false,
                                      
                                    
                                )
                            ]
                        )
                    }
                }
            }

        }

}
