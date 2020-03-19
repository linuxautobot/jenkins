pipeline {
    agent any
    stages {
        stage('No-op') {
            steps {
                    sh ''' set -x 
      DomainName="http://beinformed-server:8080"; curl --Silent $DomainName &> /dev/null;
      if [ "$?" -eq "0" ]
          then
              echo "Ping Pass, Test Fail - `date`"; exit 0
          else
              echo "Ping Fail, Test Pass - `date`"
      fi '''
            }
        }
    }
    post {
        always {
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}
