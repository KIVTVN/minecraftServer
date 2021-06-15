pipeline {
  agent any
  stages {
    stage('build image') {
      steps {
        sh 'docker build -t minecraft-server . '
      }
    }

    stage('deploy') {
      steps {
        sh 'docker rm -f minecraft-server'
        sh 'docker run -d -e EULA=true -p 25565:25565 -v ${PWD}/minecraftServer:/data --name minecraft minecraft'
      }
    }

  }
}