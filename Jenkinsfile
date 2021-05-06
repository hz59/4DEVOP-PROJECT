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
               /* sh 'docker run pozos-api'
                sh 'docker run pozos-website-1.3' */
        }
    stage('Deploy with Ansible') {
               /* sh 'ansible-playbook -i hosts deploy.yml' */
                sh 'ansible-playbook -i hosts student_list.yml'
        }
}
