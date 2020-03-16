pipeline {
    agent any 
    stages {
        stage('build') {
            steps {         
                post {
    
                    script {
                        def r = sh script: 'wget -q https://testgoogle.com -O /dev/null', returnStatus: true
                        currentBuild.result = 'FAILURE' 
                        return (r == 0);
                    }
                }
            }
        }
    }
}
