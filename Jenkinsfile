pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    def buildStatus = sh(script: 'g++ -o PES2UG22CS103-1 main/hello.cpp', returnStatus: true)
                    if (buildStatus != 0) {
                        error("Build failed")
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    def testStatus = sh(script: './PES2UG22CS103-1', returnStatus: true)
                    if (testStatus != 0) {
                        error("Test failed")
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment stage - No actual deployment in this example."
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
    }
}
