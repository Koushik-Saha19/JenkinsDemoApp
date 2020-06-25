pipeline {
    agent any
<<<<<<< HEAD
    tools {
        maven 'LocalMVN'
        jdk 'LocalJDK'
    }
    stages {
        stage ('Artifactory configuration') {
            steps {
                rtServer (
                    id: "maven_lib_release_local",
                    url: "http://52.142.15.74:8081/artifactory",
                    username: "admin",
                    password: "jfrog123"

                )

                rtMavenDeployer (
                    id: "MAVEN_DEPLOYER",
                    serverId: "maven_lib_release_local",
                    releaseRepo: "libs-release-local",
                    snapshotRepo: "libs-snapshot-local"
                )
        
            }
        }
        stage ('Exec Maven') {
            steps {
                rtMavenRun (
                    pom: 'pom.xml',
                    goals: 'clean install',
                    deployerId: "MAVEN_DEPLOYER"
                )
            }
        }
    
    }
}
=======

    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean install'
                }
            }
        }
    stage ('Testing Stage') {
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
>>>>>>> 88a1f2b7b72aa246ab13298949019b345d337a83
