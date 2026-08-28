pipeline {
    agent {
        label 'kitkat'
    }

    stages {

        stage('Checkout') {
            steps {
                sh '''
                    if [ -d "login-react-python/.git" ]; then
                        cd login-react-python
                        git pull origin main
                    else
                        git clone https://github.com/Yuvankrishnastackly/login-react-python.git
                    fi
                '''
            }
        }

        stage('Docker Compose Up') {
            steps {
                sh '''
                    cd login-react-python
                    docker compose up -d
                '''
            }
        }
    }
}
