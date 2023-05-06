pipeline{
    agent any
    stages {
        stage("CI"){
            steps {
                sh """ 
                  docker build -t node-app-jenkins .
                  docker images  
                """
            }
        }
        stage("CD") {
            steps {
               sh """ 
                  docker run --name node-app-jenkins-container -p 4000:4000 node-app-jenkins 
                  docker ps 
                """
            }
        }
    }
}
