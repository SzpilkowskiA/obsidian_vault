1. Create Slack account and a workspace to work on
2. Create a channel for jenkins to post messages in
3. Go to [my slack](https://my.slack.com/services/new/jenkins-ci) to add Jenkins and specify earlier created jenkins channel
4. follow the instructions in next page


post actions for slack promoscan
```
post {  
         always {
             script {
                slackSend channel: "#jenkins-builds", tokenCredentialId: "jenkins_slack_integration_token", message: "Build Started - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", color: "#4c9bd5"
             }
         }  
         success {  
             script {
                slackSend channel: "#jenkins-builds", tokenCredentialId: "jenkins_slack_integration_token", message: "Build Success - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", color: "#8bc14e"
             }
         }  
         failure {  
             script {
                slackSend channel: "#jenkins-builds", tokenCredentialId: "jenkins_slack_integration_token", message: "Build Failure - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", color: "#d54b53"
             }
         }  
         unstable {  
             script {
                slackSend channel: "#jenkins-builds", tokenCredentialId: "jenkins_slack_integration_token", message: "Build Unstable - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", color: "#f6b44a"
             }
         }  
         changed {  
             script {
                slackSend channel: "#jenkins-builds", tokenCredentialId: "jenkins_slack_integration_token", message: "Build Changed - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", color: "#949393"
             }
         }  
     }
```