pipeline {
    agent any

    stages {
        stage('Build') {
            steps {        
                echo 'Build'
                echo 'Test' 
                sh "mkdir output"
                sh "echo ${env.BUILD_ID} > ${env.WORKSPACE}/output/myfile.txt"
                echo "${env.WORKSPACE}"
                sh "ls ${env.WORKSPACE}"
                stash includes: "output/myfile.txt", name: "data"                 
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
                script {                
                myVar = readFile('output/myfile.txt')
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
