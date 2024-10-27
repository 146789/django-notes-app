@Library("Shared") _
pipeline{
    
    agent { label "naveen" }
    
    stages {
        stage("hello") {
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code") {
            steps{
                script {
                    
                    clone("https://github.com/146789/django-notes-app.git", "main")   
                }
            }
            
        }
        stage("Build") {
            steps{
                script {
                    docker_build("notes-app", "latest", "naveensrt248")
                }
            }   
        }
        stage("Push to DockerHub") {
            steps{
                script{
                    docker_push("notes-app", "latest","naveensrt248")   
                }
                
            }          
        }
        stage("Deploy") {
            steps{
                script{
                    docker_compose()
                }
            }
            
        }
    }
}
