pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                script{
                    build()
                }
            }
        }
        stage('deploy-to-dev') {
            steps {
                script {
                    echo "deploying to dev"
                }
            }
        }
        stage('tests-on-dev') {
            steps {
                script {
                    echo "testing dev"
                }
            }
        }
        stage('deploy-to-staging') {
            steps {
               script {
                    echo "deploying to staging"
                }
            }
        }
        stage('tests-on-staging') {
            steps {
                script {
                    echo "testing staging"
                }
            }
        }
        stage('deploy-to-preprod') {
            steps {
                script {
                    echo "deploying to preprod"
                }
            }
        }
        stage('tests-on-preprod') {
            steps {
                script {
                    echo "testing preprod"
                }
            }
        }
        stage('deploy-to-prod') {
            steps {
                script {
                    echo "deploying to prod"
                }
            }
        }
        stage('tests-on-prod') {
            steps {
                script {
                    echo "testing prod"
                }
            }
        }
    }
}

def build(){
    dir("C:\\Users\\kkoki\\Desktop\\python-greetings") {
        echo "Starting to clone python-greetings repo"
        git branch: 'main', changelog: false, poll: false, url: 'https://github.com/mtararujs/python-greetings.git'
        bat "dir C:\\Users\\kkoki\\Desktop\\python-greetings"
        echo "Installing dependencies for python repo project"
        bat "pip install -r requirements.txt"
    }    
}

