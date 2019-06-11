pipeline {
    agent any

    stages {
        stage('Build') {
            steps {        
                echo 'Build'
                echo 'Test'   
                var = "KRCARD"                     
            }
        }        
        stage('QA') {
            timeout(time: 2, unit: 'MINUTES')
            steps {
                input('Do you want to proceed?')
                echo 'Build'
                echo 'Test'
                echo "${var}"
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