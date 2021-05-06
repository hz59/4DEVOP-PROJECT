node {
    
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {

   /*     def customImage = docker.build("hzsupinfo/projet-devop-zl")

        customImage.push() */
    }
    stage('Build') {
                /*sh 'docker-compose build'
                sh 'docker-compose up -d'*/
              /*  sh 'docker container run pozos-api'
                sh 'docker container run pozos-website-1.3' */
        }
    stage('Deploy with Ansible') {
                sh 'ansible-playbook -i hosts install.yml' 
                sh 'ansible-playbook -i hosts student_list.yml'
        }
    stage('Deploy with Ansible') {
                sh 'ansible-playbook -i hosts install.yml' 
                sh 'ansible-playbook -i hosts student_list.yml'
        }
   /* stage('analyze') {
            steps {
                writeFile file: "anchore_images", text: "docker.io/hzsupinfo/projet-devop-zl:${BUILD_ID}"
                anchore name: 'anchore_images',bailOnFail: true, bailOnPluginFail: true
            }
        } */
    } 
}
