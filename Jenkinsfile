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
                timeout(time: 10, unit: 'MINUTES')
                input('Do you want to proceed?')
                echo 'Build'
                echo 'Test'
            }
        }
        stage('Stage') {
            steps {
                input('Do you want to proceed?')
                echo 'Build'
                echo 'Test'
            } 
        }
        stage('Prod') {
            steps {
                input('Do you want to proceed?')
                echo 'Build'
                echo 'Test'
            }
        }
    }
}