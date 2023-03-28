
pipeline{
    agent any
    

    stages{
        stage("clone"){
            steps{
                git "https://github.com/nileshyav/simple-website.git"
            }
        }
    stage("Build"){
        steps{
            
            script{
                app = docker.build("nileshyav/simpleapp:v1")
            }
            
        }
    }

    stage("Push to dockerhub"){
        steps{
            script{
                withDockerRegistry(credentialsId:"dockerhub1",url:''){
                  app.push("latest:${env.BUILD_NUMBER}")
                    
                }

            }

        }
    }
    }
}