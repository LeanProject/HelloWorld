// blank
def Culprit   = emailextrecipients([[$class: 'CulpritsRecipientProvider']])
// tl@leanproject.dk
def Developer = emailextrecipients([[$class: 'DevelopersRecipientProvider']])
// tla@gmail.com
def to = emailextrecipients([[$class: 'RequesterRecipientProvider']])

node {
     stage ('Send mail') {
        java -verdion 
        if (to != null && !to.isEmpty()) {
        // Email on any failures, and on first success.
            if (currentResult != 'SUCCESS' || currentResult != previousResult) { 
            emailext(body: '${DEFAULT_CONTENT}', 
                     mimeType: 'text/html',
                     replyTo: '$DEFAULT_REPLYTO', 
                     subject: '${DEFAULT_SUBJECT}',
                     from: "jenkins@tv2.dk",
                     to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                                             [$class: 'RequesterRecipientProvider']])) 
                
            }
            echo 'Sent email notification'
        }
        /*mail (to: to,
         subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) is waiting for input",
         body: "Please go to ${env.BUILD_URL}.");*/
      } //stage   
} //node
