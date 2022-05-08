
pipeline {
    agent { docker { image 'python:3.5.1' }}
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'python:2-alpine'
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
        stage('Print') {
            agent {
                docker {
                    image 'python:3.8'
                }
            }
            steps {
                sh "python -m sources.print ${BUILD_NUMBER} ${env.BRANCH_NAME}"
                sh '''
                    echo 352
                    python -m sources.print \
                    625 \
                    224
                '''
                sh "echo ${env.NODE_NAME}"
                sh "python --version"
            }
        }
    }
}
