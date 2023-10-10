pipline {
agent any
  tools {
    maven 'maven'
  }
  stages {
    stage ("Clean up"){
      steps {
        deleteDir()
      }
    }
    stage ("Clone repo")
    steps {
      sh " git clone https://github.com/ghofranechaouachi/jenkinspring.git"
    }
  }
  stage ("Generate backend image") {
    steps {
      dir ("jenkinspring") {
        sh "mvn clean install"
        sh "docker build -t docexp1-spring ."
      }
    }
  }
  stage ("Run docker compose") {
    steps {
      dir("jenkinspring") {
        sh "docker compose up -d"
      }
    }
  }
}
