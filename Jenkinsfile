pipeline {
    agent any
    tools {
        maven 'LocalMVN'
        jdk 'LocalJDK'
    }
    stages {
        stage ('Build') {
            steps {
                sh 'mvn clean install'
                sh 'curl -T /var/lib/jenkins/workspace/Complete-CI-CD-with-Jmeter-Test/target/JenkinsDemoApp.war "http://tomcat:tomcat@137.117.85.109:8080/manager/text/deploy?path=/JenkinsDemoApp&update=true"
'
            }
        }
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
