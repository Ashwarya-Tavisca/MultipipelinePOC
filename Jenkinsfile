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
                echo "${params.RELEASE_ENVIRONMENT}"
                }
        }
        stage('''${env.BUILD_ID}''') {          
             steps {
                 echo "${params.RELEASE_ENVIRONMENT}"
                 script {
                 if("${params.RELEASE_ENVIRONMENT}" == 'Build' || "${params.RELEASE_ENVIRONMENT}" == 'QA') {
                     echo "BUILD OR QA"                    
                 }
                else if ("${params.RELEASE_ENVIRONMENT}" == 'Stage')  {                
                    echo "Stage"
                }
                else if ("${params.RELEASE_ENVIRONMENT}" == 'Prod')   {
                     echo "Prod"  
                }
              }
             }
         } 
              
    }
}
