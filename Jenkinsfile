pipeline {
    agent any
    stages {
        stage ('Build')
        {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true clean install'
            }
            post {
                success{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
