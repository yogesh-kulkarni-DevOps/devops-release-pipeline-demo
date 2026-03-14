pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Backend') {
            steps {
                dir('backend-java/employee-service') {
                    bat 'mvn clean package'
                }
            }
        }

        stage('Run Database Migration') {
            steps {
                dir('backend-java/employee-service') {
                    bat 'mvn liquibase:update'
                }
            }
        }

    }

}