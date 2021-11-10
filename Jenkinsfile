pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Building'
                
                timeout(time: 3, unit: 'MINUTES') {
                    retry(5) {
                        sh './test.sh'
                    }
                }
            }
        }
        
        stage('test') {
            steps {
                echo 'Testing'

            }
        }
        
        stage('deploy') {
            steps {
                echo 'Deploying'

            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
