// Jenkinsfile.deploy
pipeline {
    agent any
    parameters {
        string(name: 'IMAGE_NAME', defaultValue: 'moha011/jenkins_node:iti', description: 'Docker image to deploy')
    }
    stages {
        stage('Deploy Application') {
            steps {
                script {
                    sh """
                        docker stop running_app || true
                        docker rm running_app || true
                        docker run -d \
                            --name running_app \
                            -p 3000:3000 \
                            ${params.IMAGE_NAME}
                    """
                }
            }
        }
    }

}
