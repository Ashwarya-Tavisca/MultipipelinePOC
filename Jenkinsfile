pipeline {
    agent any

    stages {
        stage('Build') {
            steps {                
                input('Do you want to proceed?')
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