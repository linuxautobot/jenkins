pipeline {
    agent any 
    stages {
        stage('build') {
            steps {         
            
            timeout(5) {
                        waitUntil {
                           script {
                             def r = sh script: 'wget -q https://google.com -O /dev/null', returnStatus: true
                            currentBuild.result = 'SUCCESS' 
                            return (r == 0);
                           }
                        }
                    }
            }
        }
    }
}
