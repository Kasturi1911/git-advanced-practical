pipeline {
    agent any 
    stages {
        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building... Generating artifacts.'
                sh 'echo "Build Successful" > build_output.txt'
            }
        }
        stage('Echo Build Status') {
            steps {
                script {
                    echo "The current build status is: ${currentBuild.result ?: 'SUCCESS'}"
                }
            }
        }
        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'build_output.txt', fingerprint: true
            }
        }
    }
}
