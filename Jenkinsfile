pipeline {
    agent any
    stages {
        stage('No-op') {
            steps {
 
                        url="https://google.com"

                        int status = sh(script: "curl -sLI -w '%{http_code}' $url -o /dev/null", returnStdout: true)

                        if (status != 200 && status != 201) {
                            error("Returned status code = $status when calling $url")
                        }



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
