pipeline {
  agent {
    docker {
      image 'maven:3.8.5-openjdk-17'
    }
  }

  stages {
    stage('Build') {
      steps {
         script {
                    docker.image('maven:3.8.5-openjdk-17').inside('-v $HOME/.m2:/root/.m2') 
                }
        sh 'mvn clean package'
      }
    }

    stage('Run') {
      steps {
        sh 'java -cp target/java-hello-jenkins-1.0-SNAPSHOT.jar com.example.HelloJenkins'
      }
    }
  }
}

