node {
    stage('Clone repository') {
        git credentialsId: 'github-access-token', url: 'https://github.com/HwangChulHee/jenkins-test.git'
    }

    stage('Build image') {
       dockerImage = docker.build("blackbori/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
