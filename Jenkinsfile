pipeline {
    agent any
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
    }
    stages {
        stage('Hello') {
            steps {
                sh '''
                    java -version
                '''
                sh """echo "Running newman tests with version"
                newman -v

            }
        }
    }
}
