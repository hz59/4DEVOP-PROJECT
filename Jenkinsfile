node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-id') {
/*
        def customImage = docker.build("hzsupinfo/4devop-projet")

        customImage.push()*/
    } 
    /*stage('Deploy') {
                sh 'docker-compose build'
                sh 'docker-compose up -d'
        }*/
    stage('Deploy with Ansible') {
                sh 'ansible-playbook -i hosts student_list.yml'
        }
}
