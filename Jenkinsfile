@Library('hibernate-jenkins-pipeline-helpers@1.5') _

pipeline {
    agent {
        label 'Worker&&Containers'
    }
    tools {
        maven 'Apache Maven 3.8'
        jdk 'OpenJDK 17 Latest'
    }
    options {
        buildDiscarder logRotator(daysToKeepStr: '30', numToKeepStr: '10')
        disableConcurrentBuilds(abortPrevious: false)
    }
    stages {
        stage('Build') {
            steps {
                sh "mvn -B clean verify"
            }
        }
    }
}
