pipeline {
    agent { label 'master' }
    stages {
       stage('test') {
        post {
            always {
              script {
                            def r = sh script: 'wget -q https://testgoogle.com -O /dev/null', returnStatus: true
                            currentBuild.result = 'FAILURE' 
                            return (r == 0);
                        }
            }
            failure {
              sh ' echo This will run only if failed'
            }
            changed {
              sh ' echo This will run only if the state of the Pipeline has changed'
            }
         }

         steps {
             sh ' echo fail me please'
         }
       }
    }
}
