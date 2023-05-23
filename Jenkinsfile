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
                    deploy('dev', 7001)
                }
            }
        }
        stage('tests-on-dev') {
            steps {
                script {
                    test('dev')
                }
            }
        }
        stage('deploy-to-staging') {
            steps {
               script {
                    deploy('staging', 7002)
                }
            }
        }
        stage('tests-on-staging') {
            steps {
                script {
                    test('staging')
                }
            }
        }
        stage('deploy-to-preprod') {
            steps {
                script {
                    deploy('preprod', 7003)
                }
            }
        }
        stage('tests-on-preprod') {
            steps {
                script {
                    test('preprod')
                }
            }
        }
        stage('deploy-to-prod') {
            steps {
                script {
                    deploy('prod', 7004)
                }
            }
        }
        stage('tests-on-prod') {
            steps {
                script {
                    test('prod')
                }
            }
        }
    }
}

def build() {
    echo "Starting to clone python-greetings repo"
    git branch: 'main', changelog: false, poll: false, url: 'https://github.com/mtararujs/python-greetings.git'
    bat "dir"
    echo "Installing dependencies for python repo project"
    bat "pip install -r requirements.txt"   
}

def deploy(String env, int port) {
    echo "Starting deployment to ${env}"
    echo "Pulling in changes from main branch"
    git branch: 'main', changelog: false, poll: false, url: 'https://github.com/mtararujs/python-greetings.git'
    echo "deleting the app"
    bat "C:\\Users\\kkoki\\AppData\\Roaming\\npm\\pm2 delete greeting-app-${env} & EXIT /B 0"
    echo "starting the app"
    bat "C:\\Users\\kkoki\\AppData\\Roaming\\npm\\pm2 start app.py --name greeting-app-${env} -- --port ${port}"
}

def test(String env) {
    echo "Testing ${env}"
    echo "Pulling in changes from main branch"
    git branch: 'main', changelog: false, poll: false, url: 'https://github.com/mtararujs/course-js-api-framework.git'
    echo "Installing dependancies"
    bat "npm install"
    bat "npm run greetings greetings_${env}"
}