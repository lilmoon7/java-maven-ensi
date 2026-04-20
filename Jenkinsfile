pipeline {
agent {
  docker {
  // Image contenant Maven et Git
  image 'my-maven-git:latest'
  // Pour réutiliser le cache Maven local entre builds
  //args '-v $HOME/.m2:/root/.m2'
  args '-v maven-repo:/root/.m2 -u root'
  }
}
stages {
stage('Checkout') {
  steps {
  // clean the directory
  sh "rm -rf *"
  // Checkout the Git repository
  //sh "git clone https://github.com/simoks/java-maven-ensi.git"
    checkout scm
  }
}
stage('Build') {
  steps {
    script {
    // Here, we can can run Maven commands
    def currentDir = pwd()
    echo "Current directory: ${currentDir}"
    // Navigate to the directory containing the Maven project
      dir('maven') {
      // Run Maven commands
      sh 'mvn clean test package'
      sh "java -jar target/maven-0.0.1-SNAPSHOT.jar"
      }
    }
  }
}
}
}
