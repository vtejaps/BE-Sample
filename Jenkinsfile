pipeline {
    agent {
        node {
            label 'ubuntu-PS'
        }
    }
    tools {
        maven 'Maven'
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh "mvn clean install"
                }
            }
        }
        stage('SonarQube Analysis') {
            steps {
                script {
                    def mvn = tool 'Maven'
                    withSonarQubeEnv() {
                        sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=BE-Sample"
                    }
                }
            }
        }
    }
}
