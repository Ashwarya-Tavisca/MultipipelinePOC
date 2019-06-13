pipeline {
    agent any

    stages {
        stage('Build') {
            when {
                expression { check () }
            }
            steps {
                echo "Hello"
            }
        } 
              
    }
}
def check() {
 return true;
}