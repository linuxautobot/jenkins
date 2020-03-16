pipeline {
    agent { label 'master' }
    stages {
       stage('test') {
        post {
            always {
              sh ' echo This will always run'
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
