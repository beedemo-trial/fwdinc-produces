node {
    stage ('checkout') {
        checkout scm
    }
    stage ('build') {
        // Print Message
        echo 'Hello World!'
        
        // Creates a file called plugin-a.txt.
        sh "git rev-parse HEAD > plugin-a.txt"

        // Records plugin-a.txt as a produced artifact.
        archiveArtifacts artifacts: 'plugin-a.txt'
    }
    stage ('produce') {
        // Notify DevOptics that this run produced plugin-a.txt.
        gateProducesArtifact file: 'plugin-a.txt'
    }
}
