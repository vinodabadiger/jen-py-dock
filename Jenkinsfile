def img
pipeline{
    agent any
    environment{
    registry = "vinoda32/python"
    }
        stages{

            stage('checkout'){
                steps{
                    git branch: 'main', credentialsId: 'git-cred', url: 'https://github.com/vinodabadiger/jen-py-dock.git'
                }  
            } 

            // stage('build'){
            //     steps{
            //         script{
            //         img = registry + ":${env.BUILD_ID}"
            //         print "${img}"
            //         sh "docker build -t $img ." 
            //         }
            //     }  
            // } 

             
            // stage('push'){
            //     steps{
            //         withDockerRegistry(credentialsId: 'docker-cred', url: 'https://index.docker.io/v1/') {
            //           sh " docker push $img "
            //         }  
            //    }
            // }

            // stage('ssh'){
            //     steps{
            //         script{
            //             sshPublisher(
            //                 publishers: [
            //                     sshPublisherDesc(
            //                         configName: 'production',
            //                         verbose: true ,
            //                             transfers: [
             
            //                                 // sshTransfer(
            //                                 //         execCommand: 'cat ~/pass.txt |docker login https://index.docker.io/v1/ --username $duser --password-stdin', 
            //                                 //         execTimeout: 120000
            //                                 // ),

            //                                 sshTransfer(
            //                                         execCommand: 'docker images', 
            //                                         execTimeout: 120000
            //                                 ),

            //                                 sshTransfer(
            //                                         execCommand: 'docker ps', 
            //                                         execTimeout: 120000
            //                                 ),

            //                                 sshTransfer(
            //                                         execCommand: "docker stop python ", 
            //                                         execTimeout: 120000
            //                                 ),

            //                                 sshTransfer(
            //                                         execCommand: "docker rm python", 
            //                                         execTimeout: 120000
            //                                 ),

            //                                 sshTransfer(
            //                                         execCommand: 'docker images', 
            //                                         execTimeout: 120000
            //                                 ),

            //                                 sshTransfer(
            //                                         execCommand: "docker ps", 
            //                                         execTimeout: 120000
            //                                 ),

            //                                  sshTransfer(
            //                                         execCommand: "docker pull $img", 
            //                                         execTimeout: 120000
            //                                 ),

            //                                  sshTransfer(
            //                                         execCommand: "docker run -d -p 8080:8080 --name=python $img", 
            //                                         execTimeout: 120000
            //                                 ),
                                            
            //                             ], 

            //                         usePromotionTimestamp: false, 
            //                         useWorkspaceInPromotion: false
                                    
            //                     )
            //                 ]
            //             )
            //         }
            //     }
           
          
            // }

            // stage('cleanup'){
            //     steps{
            //        sh "docker rmi $img "
            //     }  
            // }
        }

}
