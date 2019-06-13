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
                   script {
                RELEASE_ENVIRONMENT1 = "${params.RELEASE_ENVIRONMENT}"
                   }
                echo "${RELEASE_ENVIRONMENT1}"
            }
        }
        // stage("${params.RELEASE_ENVIRONMENT}") {          
        //     steps {
        //         script {
        //         if("${params.RELEASE_ENVIRONMENT}" == 'Build' || "${params.RELEASE_ENVIRONMENT}" == 'QA') {
        //             echo "BUILD OR QA"                    
        //         }
        //         else if ("${params.RELEASE_ENVIRONMENT}" == 'Stage')  {                
        //             echo "Stage"
        //         }
        //         else if ("${params.RELEASE_ENVIRONMENT}" == 'Prod')   {
        //              echo "Prod"  
        //         }
        //      }
        //     }
        // } 
              
    }
}
