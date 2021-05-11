pipeline {
  environment {
    registry = 'registry.hub.docker.com'
    registryCredential = 'dockerhub'
    /*repository = 'hzsupinfo/projet-devop-zl'*/
   /* imageLine = 'registry.hub.docker.com/hzsupinfo/projet-devop-zl:latest'*/
  }
  agent any
  stages {
    stage('Checkout SCM') {
      steps {
        checkout scm
      }
    }
    stage('Build image') {
      steps {
        sh 'docker --version'
        sh 'docker build .'
        sh 'docker run -d -p 5000:5000 -v' 
        sh 'curl -u toto:python -X GET http://192.168.56.103:5000/pozos/api/v1.0/get_student_ages'
        script {
          docker.withRegistry('https://' + registry, registryCredential) {
            writeFile file: "anchore_images", text: "docker.io/hzsupinfo/projet-devop-zl:${BUILD_ID}"
            anchore name: 'anchore_images',bailOnFail: true, bailOnPluginFail: true
            image.push()
          }
        }
      }
    }
      stage('Deploy with Ansible') {
      steps {
        sh 'ansible-playbook -i hosts install.yml' 
        sh 'ansible-playbook -i hosts student_list.yml'
      }
    }
    stage('E2E Tests') {
         steps {
            arachniScanner checks: '*', scope: [pageLimit: 3], url: 'http://192.168.56.102:8003', userConfig: [filename: 'myConfiguration.json'], format: 'json'
         }
      }
  }
}
