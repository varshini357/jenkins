pipeline {
  agent {
    docker {
      image 'maven:3.8.5-openjdk-17'
    }
  }

  stages {
    stage('Build') {
      steps {
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

