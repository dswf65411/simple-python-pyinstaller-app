pipeline {
    agent {
        docker {
            image 'python:3.6'
        }
    }   // 整個 pipeline 都用此 image，agent 也叫 node
    stages {
        agent {
            docker {
                image 'python:3.8'
            }
        }
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
    }
}
