pipeline {
    agent any
    stages {
        stage ('Build Eureka') {
            steps {
                bat 'mvn clean package -DskipTests=true'
            }
        }
        stage ('Unit Tests') {
            steps {
                bat 'mvn test'
            }
        }
        stage ('Sonar Analise') {
            environment {
                scannerHome = tool 'SONAR_SCANNER'
            }
            steps {
                withSonarQubeEnv('LOCAL') {
                    bat "${scannerHome}/bin/sonar-scanner -e -Dsonar.projectKey=Sistema -Dsonar.host.url=http://localhost:9000 -Dsonar.login=sqp_808943bf5f1facb2b5c7606b81ed0911279f49a4 -Dsonar.working.directory=/workspace/target/.sonar"
                }
            }
        }
    }
}