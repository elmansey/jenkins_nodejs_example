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
                  docker run --name node-app-jenkins-container -d -p 3000:3000 node-app-jenkins 
                  docker ps 
                """
            }
        }
    }
}
