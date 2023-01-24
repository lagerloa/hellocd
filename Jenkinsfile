pipeline { 
    agent any 

    stages { 
         stage('Hello') { 
             steps { 
                 echo 'Hello World' 
             } 
         } 
    }

    post{ 
        always{ 
            echo 'Pipeline completed successfully' 
        } 
        failure{ 
            slackSend (channel: "#ci-cd", message: "Build Failed: ${env.JOB_NAME} ${env.BUILD_NUMBER}") 
        } 
        success{ 
            slackSend (channel: "#ci-cd", message: "Build Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}") 
        } 
    } 
}
