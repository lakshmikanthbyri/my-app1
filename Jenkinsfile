pipeline {
    agent any
    stages {
        stage ('Build on master')
        {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true clean install'
            }
            post {
                success{
                    archiveArtifacts artifacts: 'target/**/*.jar', fingerprint: true
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage ('Build on develop')
        {
          steps {
                sh 'mvn -Dmaven.test.failure.ignore=true clean install'
            }
            post {
                success{
                    archiveArtifacts artifacts: 'target/**/*.jar', fingerprint: true
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
