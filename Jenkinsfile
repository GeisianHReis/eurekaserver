pipeline {
    agent any
    stages {
        stage ('Build Eureka') {
            steps {
                bat 'mvn clean package -DskipTest=true'
            }
        }
    }
}