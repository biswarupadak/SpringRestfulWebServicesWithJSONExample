pipeline {
  agent none
  stages {
    stage('Build Application') {
      steps {
        build(job: 'maven_build_spring_example', quietPeriod: 5, propagate: true, wait: true)
      }
    }
  }
}