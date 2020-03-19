import groovy.json.JsonSlurper 

pipeline {
    agent any
    stages {
        stage('No-op') {
            steps {
 
                 script {
                    response = sh(
                    returnStdout: true, 
                    script: "curl -i  https://google.com "
                    );
                    // The response is now in the variable 'response'

                    // Then you can regex to read the status. 
                    // For some reasen, the regex needs to match the entire result found.
                    // (?s) was necessary for the multiline response.
                        def jsonSlurper = new JsonSlurper()
                        def data = jsonSlurper.parseText("${response}")
                        return data.id
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
