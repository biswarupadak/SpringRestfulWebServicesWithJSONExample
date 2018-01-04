pipeline {
  agent none
  stages {
    stage('Build Application') {
      steps {
        build(job: '	Centos-Docker-Wildfly-SpringJSON/maven_build_spring_restfulwebservices_with_json', quietPeriod: 5, propagate: true, wait: true)
      }
    }
    stage('Docker Image Build') {
      steps {
        build '	Centos-Docker-Wildfly-SpringJSON/centos-docker-wildfly-job'
      }
    }
    stage('Push Docker Image') {
      steps {
        build '	Centos-Docker-Wildfly-SpringJSON/centos-wildfly-image-push'
      }
    }
    stage('Deploy to GCP k8s Dev Cluster') {
      steps {
        build '	Centos-Docker-Wildfly-SpringJSON/gcp-kubernetes-deployment'
      }
    }
  }
}