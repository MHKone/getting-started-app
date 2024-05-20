pipeline {
    agent any
    stages {  // Move this block one level to the right
        stage('Clone'){
            steps {
                git branch: 'main', url:'https://github.com/MHKone/Hello_Jenkins.git'
            }
        }
        stage('Build Image'){
            steps {
                withDockerRegistry(credentialsId: '0f300095-ecbb-466f-a577-ac8bdb00982a', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t mhkone113/jenkins_image:v1.0.'
                    sh 'docker push -t mhkone113/jenkins_image:v1.0.'
                }
            }

        }
    }
}