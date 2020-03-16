pipeline {
    agent { label 'master' }
       stage('test') {
                    def cmd = 'curl -i  https://testgoogle.com'
                    println "cmd[${cmd}]" 
                    def usersJson   = sh(returnStdout: true, script:cmd)
                    println "Past curl call."      
        }
             steps {
             sh ' echo fail me please'
         }
    
}
