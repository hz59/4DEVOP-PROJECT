pipeline {
  environment {
    registry = 'registry.hub.docker.com'
    registryCredential = 'dockerhub'
    repository = 'hzsupinfo/projet-devop-zl'
    imageLine = 'registry.hub.docker.com/hzsupinfo/projet-devop-zl:latest'
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
       /* sh 'docker --version'
        sh 'docker build .'
        sh '/usr/local/bin/docker-compose up -d' */
        script {
          docker.withRegistry('https://' + registry, registryCredential) {
            def image = docker.build(repository)
            /*image.push()*/
          }
        }
      }
    }  
    stage('Analyze with Anchore plugin') {
      /*steps {
        writeFile file: 'anchore_images', text: imageLine
        anchore name: 'anchore_images'
      }*/
    }
    /*stage('Build and push stable image to registry') {
      steps {
        script {
          docker.withRegistry('https://' + registry, registryCredential) {
            def image = docker.build(repository + ':prod')
            image.push()  
          }
        }
      }
    }*/
      stage('Deploy with Ansible') {
      steps {
        sh 'ansible-playbook -i hosts install.yml' 
        sh 'ansible-playbook -i hosts student_list.yml'
      }
    }
  }
}
