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
            steps {
                echo "Build"
            }
        }
        stage("DEPLOY") {   
            when {                
                expression { ${params.RELEASE_ENVIRONMENT} == 'Build' }
            }
            steps {
                echo "Build"
            }
            when {                
                expression { ${params.RELEASE_ENVIRONMENT} == 'QA' }
            }
            steps {
                echo "QA"
            }
            when {                
                expression { ${params.RELEASE_ENVIRONMENT} == 'Stage' }
            }
            steps {
                echo "Stage"
            }
            when {                
                expression { ${params.RELEASE_ENVIRONMENT} == 'Prod' }
            }
            steps {
                echo "Prod"
            }
        }       
             
    }
} 
              

