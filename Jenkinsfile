node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-id') {
/*
        def customImage = docker.build("hzsupinfo/4devop-projet")

        customImage.push()*/
    } 
    stage('Build') {
                sh 'docker-compose build'
                sh 'docker-compose up -d'
                sh 'docker container run pozos-api'
                sh 'docker container run pozos-website' 
        }
    stage('Deploy with Ansible') {
               /* sh 'ansible-playbook -i hosts deploy.yml' */
                sh 'ansible-playbook -i hosts student_list.yml'
        }
}
