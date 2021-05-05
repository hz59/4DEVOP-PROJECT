node {
/*
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-id') {

        def customImage = docker.build("hzsupinfo/4devop-projet")

        customImage.push()
    } */
    stage('Deploy') {
                sh 'sudo docker-compose build'
                sh 'sudo docker-compose up -d'
        }
}
