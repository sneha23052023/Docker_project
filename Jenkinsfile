
de {

    stage('Checkout') {

        checkout scm

    }

    stage('Verify Project') {

        sh '''
            pwd
            ls -ltr
        '''

    }

    stage('Build Images') {

        sh '''
            docker compose build
        '''

    }

    stage('Deploy') {

        sh '''
            docker compose down || true
            docker compose up -d
        '''

    }

    stage('Health Check') {

        sh '''
            curl --noproxy "*" http://127.0.0.1:5555/users
        '''

    }
}
