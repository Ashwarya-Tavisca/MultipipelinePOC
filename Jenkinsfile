pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                //sh "mkdir /opt/jenkins/workspace/Kubernetes-DevOps/stash/${env.BUILD_ID}"
                sh "echo ${env.BUILD_ID} > /opt/jenkins/workspace/Kubernetes-DevOps/stash/test1.txt"
                //stash includes: "/opt/jenkins/workspace/Kubernetes-DevOps/stash/${env.BUILD_ID}.txt", name: "data"
                sh "cd /opt/jenkins/workspace/Kubernetes-DevOps/stash/"
                stash includes: "*.txt", name: "data"
                sh "cd ${env.WORKSPACE}"
                echo "cat /opt/jenkins/workspace/Kubernetes-DevOps/stash/test1.txt"
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
                sh "pwd"
                sh "ls"
                script {                
                myVar = readFile("test1.txt")
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
