node {
/*
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-id') {

        def customImage = docker.build("hzsupinfo/4devop-projet")

        customImage.push()
    } */
    /*environment {
        PATH = "$PATH:/usr/local/bin/"
    }*/
    stage('Deploy') {
                sh 'docker-compose build'
                sh 'docker-compose up -d'
        }
}
