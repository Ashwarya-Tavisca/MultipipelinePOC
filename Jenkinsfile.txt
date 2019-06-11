pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                echo 'Test'
            }
        }
        stage('QA') {
            steps {
                echo 'Build'
                echo 'Test'
            }
        }
        stage('Stage') {
            steps {
                echo 'Build'
                echo 'Test'
            } 
        }
        stage('Prod') {
            steps {
                echo 'Build'
                echo 'Test'
            }
        }
    }
}