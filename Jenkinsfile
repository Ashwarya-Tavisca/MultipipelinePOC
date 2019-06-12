pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                sh "mkdir /opt/jenkins/workspace/Kubernetes-DevOps/stash"
                sh "echo ${env.BUILD_ID} > /opt/jenkins/workspace/Kubernetes-DevOps/stash/${env.BUILD_ID}.txt"
                stash includes: "/opt/jenkins/workspace/Kubernetes-DevOps/stash/${env.BUILD_ID}.txt", name: "data"
                echo "cat /opt/jenkins/workspace/Kubernetes-DevOps/stash/${env.BUILD_ID}.txt"
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
                myVar = readFile("/opt/jenkins/workspace/Kubernetes-DevOps/stash/${env.BUILD_ID}.txt")
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
