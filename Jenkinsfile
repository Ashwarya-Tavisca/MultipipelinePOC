pipeline {
    agent any

    stages {
        stage('Build') {
            when {
                expression { VerifyJiraCard ("Hello") }
            }
            steps {
                echo "Hello"
            }
        } 
              
    }
}
def VerifyJiraCard(text) {
    if(text == "Hey")
        return true;
    else
        return false;   
}