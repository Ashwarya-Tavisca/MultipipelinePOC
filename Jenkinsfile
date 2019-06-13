pipeline {
    agent any
     parameters {
        string (
            defaultValue: '',
            description: '',
            name : 'JIRA_CARD')            
        string (
            defaultValue: '',
            description: '',
            name : 'REPO_NAME'
        )
        choice(
        name: 'RELEASE_ENVIRONMENT',
        choices: "Build\nQA\nStage\nProd",
        description: '' )      
    }

    stages {     
        stage('Build') {
            when {                
                expression { "${params.RELEASE_ENVIRONMENT}" == 'Build' }
            }
            steps {
                echo "Build"
            }
        }
         stage('QA') {
            when {                
                expression { "${params.RELEASE_ENVIRONMENT}" == 'QA' }
            }
            steps {
                echo "QA"
            }
        }
         stage('Stage') {
            when {                
                expression { "${params.RELEASE_ENVIRONMENT}" == 'Stage' }
            }
            steps {
                echo "Stage"
            }
        }
        stage('Prod') {   
            when {                
                expression { "${params.RELEASE_ENVIRONMENT}" == 'Prod' }
            }
            steps {
                echo "Prod"
            }
        } 
             
    }
} 
              

