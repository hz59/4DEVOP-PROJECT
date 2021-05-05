node {
/*
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-id') {

        def customImage = docker.build("hzsupinfo/4devop-projet")

        customImage.push()
    } */
    stage('Deploy') {
                sh '/usr/local/bin/docker-compose build'
                sh '/usr/local/bin/docker-compose up -d'
        }
}
