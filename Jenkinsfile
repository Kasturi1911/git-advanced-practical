node {
    stage('Clone Repository') {
        checkout scm
    }
    stage('Build') {
        echo 'Running Scripted Build...'
        // Changed 'sh' to 'bat' for Windows compatibility
        bat 'echo Scripted build successful > scripted_output.txt'
    }
    stage('Echo Build Status') {
        echo "The current build status is: ${currentBuild.result ?: 'SUCCESS'}"
    }
    stage('Archive Artifacts') {
        // This fulfills the 'Archive Artifacts' requirement
        archiveArtifacts artifacts: 'scripted_output.txt'
    }
}
