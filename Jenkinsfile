node {
    stage('Clone Repository') {
        checkout scm // Clones the scripted branch
    }
    stage('Build') {
        echo 'Running Scripted Build...'
        sh 'echo "Scripted Build Success" > scripted_output.txt'
    }
    stage('Echo Build Status') {
        // Scripted pipelines use Groovy variables directly
        echo "Build Result: ${currentBuild.result ?: 'SUCCESS'}"
    }
    stage('Archive Artifacts') {
        archiveArtifacts artifacts: 'scripted_output.txt'
    }
}
