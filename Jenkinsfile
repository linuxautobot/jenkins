import groovy.json.JsonSlurper 

pipeline {
    agent any
    stages {
        stage('No-op') {
            steps {
 
                 script {
                        def url = "https://google.com"
                        int status = sh(script: "curl -sLI -w '%{http_code}' $url -o /dev/null", returnStdout: true)
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
