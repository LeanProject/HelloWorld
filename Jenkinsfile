// Jenkins file template. Purpose of this file is building a template for all Jenkins
// pipelines. 
node {

    // Prerequisits
    checkout scm

    // Automatic build stage 
    stage('\u2705 Build automation') {

    }

    // Run unittest 
    stage ('Unit test') {
     
    }

    // Static analysis
    stage ('Static analysis') {

    }
    
    //Deploy to DEV
    stage ('DEV deploy'){
    
    }
    
    //Basic DEV acceptance test
    stage ('Basic DEV acceptance test'){
    
    }
    
    //Perform load test
    stage ('Load test'){
    
    }
    
    //Perform acceptance test
    stage ('Acceptance test') {
    
    }
    
    //Deploy to STAGE
    stage ('STAGE deploy'){
    
    }
    
    // Send mail to inform about status on this build
    currentBuild.result = "SUCCESS"
    
    // Email on any failures, and on first success.
    try {
        currentBuild.result = "SUCCESS" 
    } finally {    
         if (currentBuild.result != 'SUCCESS' || currentBuild.getPreviousBuild().result != currentBuild.result) {
             emailext(subject: '${DEFAULT_SUBJECT}',
                     to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                                             [$class: 'RequesterRecipientProvider']]),
                     replyTo: '$DEFAULT_REPLYTO',
                     attachLog: true,
                     mimeType: 'text/html',
                     body: '${DEFAULT_CONTENT}')                
            }
    }

} //End of Jenkinsfile



    
