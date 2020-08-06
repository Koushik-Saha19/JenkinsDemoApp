pipeline {
    agent any
    tools {
        maven 'LocalMVN'
        jdk 'LocalJDK'
    }
    stages {
        
        stage ('Jmeter Test') {
            steps {
               sh 'mvn jmeter:jmeter'
                
            }
        }
   
    }
    post {
        always {
                
                perfReport filterRegex: '', sourceDataFiles: '/var/lib/jenkins/workspace/Complete-CI-CD-with-Jmeter-Test/src/test/resources/test.csv'
               
        }
    }
}
