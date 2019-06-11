pipeline {
    agent any

    stages {
        stage('Build') {
            steps {        
                echo 'Build'
                echo 'Test'  
                echo "${myVar}"   
                sh 'echo KRCARD > myfile.txt'
                script {
                    myVar = readFile('myfile.txt')
                }
                echo "${myVar}"
            }
        }        
        stage('QA') {          
            steps {
                timeout(time: 1, unit: 'MINUTES')
                {
                input('Do you want to proceed?')
                }
                echo 'Build'
                echo 'Test'
                echo "${myVar}"
            }
        }
        stage('Stage') {
            steps {
               timeout(time: 1, unit: 'MINUTES')
                {
                input('Do you want to proceed?')
                }
                echo 'Build'
                echo 'Test'
            } 
        }
        stage('Prod') {
            steps {
                timeout(time: 1, unit: 'MINUTES')
                {
                input('Do you want to proceed?')
                }
                echo 'Build'
                echo 'Test'
            }
        }
    }
}