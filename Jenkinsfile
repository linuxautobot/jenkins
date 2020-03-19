pipeline {
    agent { label 'master' }
       stages('test') {
                    def cmd = 'curl -i  https://testgoogle.com'
                    println "cmd[${cmd}]" 
                    def usersJson   = sh(returnStdout: true, script:cmd)
                    println "Past curl call."      
        }
    
}
