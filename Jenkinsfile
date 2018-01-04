pipeline {
  agent none
  stages {
    stage('Build Application') {
      steps {
        build(job: 'maven_build_spring_restfulwebservices_with_json', quietPeriod: 5, propagate: true, wait: true)
      }
    }
    stage('Docker Image Build') {
      steps {
        build 'centos-docker-wildfly-job'
      }
    }
    stage('Push Docker Image') {
      steps {
        build 'centos-wildfly-image-push'
      }
    }
    stage('Deploy to GCP k8s Dev Cluster') {
      steps {
        build 'gcp-kubernetes-deployment'
      }
    }
  }
}