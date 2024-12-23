
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build the project
                sh './gradlew assemble'
            }
        }

        stage('Test') {
            steps {
                // Run the tests
                sh './gradlew test'
            }
        }
    }

    post {
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build or tests failed! Please check the logs.'
        }
    }
}

// Instructions for repository setup and testing
// 1. Fork the mock-company-webapp repository from GitHub.
// 2. Clone the forked repository to your local system using the Git CLI.
// 3. Place this Jenkinsfile in the root directory of the repository.
// 4. Commit and push the changes to your repository.
// 5. Configure Jenkins to monitor the repository and trigger builds on each commit.
// 6. Modify the SearchService to always return Collections.emptyList() to break tests.
// 7. Commit and push the breaking change, ensuring the build fails as expected.
