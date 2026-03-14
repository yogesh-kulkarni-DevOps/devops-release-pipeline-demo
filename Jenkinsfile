pipeline {

    agent any

    stages {

        stage('Build Backend') {
            steps {
                dir('backend-java/employee-service') {
                    script {
                        def mvnHome = tool 'Maven-3.9'
                        bat "${mvnHome}\\bin\\mvn clean package"
                    }
                }
            }
        }

        stage('Run Database Migration') {
            steps {
                dir('backend-java/employee-service') {
                    script {
                        def mvnHome = tool 'Maven-3.9'
                        bat "${mvnHome}\\bin\\mvn liquibase:update"
                    }
                }
            }
        }

    }
}