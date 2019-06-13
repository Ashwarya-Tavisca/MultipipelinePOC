pipeline {
    agent any

    stages {
        stage('Build') {
            when {
                expression { check ("Hey") }
            }
            steps {
                echo "Hello"
            }
        } 
              
    }
}
def check(text) {
    if(text == "Hey")
        return true;
    else
        return false;   
}