pipeline {
    agent any 
    stages {
        stage('build') {
            steps {         
            
            timeout(5) {
                        waitUntil {
                           script {
                             def r = sh script: 'wget -q http://google.com -O /dev/null', returnStatus: true
                             return (r == 100);
                           }
                        }
                    }
            }
        }
    }
}
