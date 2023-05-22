pipeline {
    agent any
    triggers{ pollSCM('*/1 * * * *') }
    

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

def build(String repoUrl){
    gitClone('https://github.com/mtararujs/python-greetings')
    pipInstall()
}

def gitClone() {
    echo "Starting to clone this repo: ${repoUrl}"
    bat "cd C:\\Users\\kkoki\\Desktop"
    git branch: 'main', poll: false, url: "${repoUrl}"
    bat "dir C:\\Users\\kkoki\\Desktop\\python-greetings"
}

def pipInstall() {
    echo "Installing dependencies for python repo project"
    bat "pip install -r requirements.txt"
}
