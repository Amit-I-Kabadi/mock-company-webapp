

// pipeline {
//   /*
//    * TODO: Implement pipeline stages/steps
//    *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
//    */
// }
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building project...'
                    sh './gradlew assemble'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh './gradlew test'
                }
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/build/libs/*.jar', allowEmptyArchive: true
        }
        failure {
            echo 'Build failed!'
        }
    }
}


