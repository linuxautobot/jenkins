pipeline {
    agent any
node ('master') {
  try{
    stage('Deployment') {
    
 sh ''' set -x 
      DomainName="http://google.com"; curl --Silent $DomainName &> /dev/null;
      if [ "$?" -eq "0" ]
          then
              echo "Ping Pass, Test Fail - `date`"; exit 0
          else
              echo "Ping Fail, Test Pass - `date`"
      fi '''

}
catch (err)
{
      stage('Send email') {/*
        def env = params.apigee_env.toLowerCase()
       def mailRecipients = "cx.alert.prd@prudential.co.uk"
       
        if(env=='nonprod'){
          print "setting email to cx.alert.nonprd@prudential.co.uk"
          mailRecipients = "cx.alert.nonprd@prudential.co.uk"
        } 
        print env
    
    def jobName = currentBuild.fullDisplayName

    emailext body: '''${SCRIPT, template="groovy-html.template"}''',
        mimeType: 'text/html',
        subject: "[Jenkins] ${jobName} FAILED",
        to: "${mailRecipients}",
        replyTo: "${mailRecipients}",
        recipientProviders: [[$class: 'CulpritsRecipientProvider']]
*/}
        echo "Failed Build"
      throw err
    }

}
