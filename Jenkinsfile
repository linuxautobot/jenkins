pipeline {
    agent Any 
    stages {
        stage('build') {
            steps {
                   sh ''' 
                          set -x 
                          DomainName="http://beinformed-server:8080"; curl --Silent $DomainName &> /dev/null;
                          if [ "$?" -eq "0" ]
                              then
                                  echo "Ping Pass, Test Fail - `date`"; exit 0
                              else
                                  echo "Ping Fail, Test Pass - `date`"
                          fi 
                     '''
            }
        }
    }
}
