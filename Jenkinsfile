pipeline {
    agent { label 'master' }
    stages {
       stage('test') {
        post {
            always {
              sh 'This will always run'
            }
            failure {
              sh 'This will run only if failed'
            }
            changed {
              sh 'This will run only if the state of the Pipeline has changed')
            }
         }

         steps {
             sh 'fail me please'
         }
       }
    }

}
