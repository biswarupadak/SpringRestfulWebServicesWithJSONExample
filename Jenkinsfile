pipeline {
  agent none
  stages {
    stage('Build Application') {
      steps {
        build(job: 'maven_build_spring_example', quietPeriod: 5, propagate: true, wait: true)
      }
    }
    stage('Docker Image Build') {
      steps {
        build 'centos-docker-wildfly-job'
      }
    }
    stage('Push Docker Imgage') {
      steps {
        build 'centos-wildfly-image-push'
      }
    }
  }
}