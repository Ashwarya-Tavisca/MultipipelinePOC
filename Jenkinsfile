pipeline {
    agent any

    stages {
        stage('Build') {
            steps {        
                echo 'Build'
                echo 'Test' 
                sh "echo ${env.BUILD_ID} > ${env.WORKSPACE}/myfile.txt"
                echo "${env.WORKSPACE}"
                stash allowEmpty: true, includes: "${env.WORKSPACE}/myfile.txt", name: "data"                 
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
                unstash 'data' 
                cat 'myfile.txt'
                script {                
                myVar = readFile('myfile.txt')
                }
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
