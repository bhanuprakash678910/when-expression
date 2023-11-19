pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            when {
                expression {
                    // Define your condition here
                    return env.BRANCH_NAME == 'main'
                }
            }
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            when {
                expression {
                    // Another condition
                    return env.BRANCH_NAME == 'main' && currentBuild.resultIsBetterOrEqualTo('SUCCESS')
                }
            }
            steps {
                echo 'Deploying...'
            }
        }
    }
}
