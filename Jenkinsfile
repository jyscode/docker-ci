node {
  stage('Clone repository') {
    git credentialsId: 'github', url: 'https://github.com/jyscode/docker-ci.git'
  }
  stage('Build image') {
    dockerImage = docker.build("readytodev/jenkins-ci:1.0")
  }
  stage('Push image') {
    withDockerRegistry([ credentialsId: "docker-hub", url: "" ]) {
  dockerImage.push()
    }
  }
}
