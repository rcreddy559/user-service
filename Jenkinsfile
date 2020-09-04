pipeline {
    agent any
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    source ~/.bash_profile
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                 sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
            post {
                success {
                    echo "------- Post Build ----------"
                }
            }
        }
    }
}
