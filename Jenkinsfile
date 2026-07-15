Pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source downloaded'
            }
        }

        stage('Verify') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Docker Build') {
            steps {
                sh '''
                docker -H tcp://192.168.213.130:2375 build -t website:1.0 .
                '''
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker -H tcp://192.168.213.130:2375 rm -f website || true
                docker -H tcp://192.168.213.130:2375 run -d \
                --name website \
                -p 8080:80 \
                website:1.0
                '''
            }
        }

    }
}