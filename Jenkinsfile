pipeline {
    agent { docker 'maven:3-alpine' }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -U -e clean install -Djava.awt.headless=false'
            }
        }
    }
    post {
        always {
            junit '**/surefire-reports/**/*.xml'
        }
    }
}
