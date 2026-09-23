
node {

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




}
