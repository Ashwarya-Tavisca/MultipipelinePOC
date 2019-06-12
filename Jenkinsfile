pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                cleanWs()
                echo 'Build'
                echo 'Test' 
                sh "echo ${env.BUILD_ID} > ${env.WORKSPACE}/${env.BUILD_ID}.txt"
                stash includes: "*.txt", name: "data"
                echo "cat ${env.WORKSPACE}/myfile.txt"
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
                sh "ls"
                script {                
                myVar = readFile("${env.BUILD_ID}.txt")
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
