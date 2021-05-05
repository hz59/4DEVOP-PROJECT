node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-id') {

        def customImage = docker.build("hzsupinfo/4devop-projet")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
