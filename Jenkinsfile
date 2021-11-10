pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                echo 'Building'
                
                retry(3) {
                    sh './flakey-deploy.sh'
                }

                timeout(time: 3, unit: 'MINUTES') {
                    sh './health-check.sh'
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
}
