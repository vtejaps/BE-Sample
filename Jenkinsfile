pipeline 
{
    agent {
            node {
        label 'ubuntu-PS'
        }
    }
    tools {
      maven 'Maven'
    }
    stages {
      stage ('Build') {
            steps{
                script {
                    sh "mvn clean install"
                }
            }
     }
}

}
