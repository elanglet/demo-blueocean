pipeline {
  agent any
  stages {
    stage('R�cup�ration du code dans Git') {
      steps {
        git(url: 'https://github.com/elanglet/projet-banque.git', branch: 'jenkins')
      }
    }

    stage('Ex�cution de la commande mvn') {
      steps {
        bat(script: 'mvn -f banque/pom.xml', returnStdout: true)
      }
    }

    stage('Publication des r�sultats de tests') {
      steps {
        junit(testResults: 'banque/*/target/surefire-results/*.xml', allowEmptyResults: true)
      }
    }

  }
}