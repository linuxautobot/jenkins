pipeline {
    agent any 
    stages {
        stage('build') {
            steps {         
                post {
                    always {
                        script {
                            def r = sh script: 'wget -q https://testgoogle.com -O /dev/null', returnStatus: true
                            currentBuild.result = 'FAILURE' 
                            return (r == 0);
                        }
                    }
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
    }
}
