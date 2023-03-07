pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('git clone') {
            steps {
                git branch: 'main', credentialsId: 'git_credentials', url: 'https://github.com/Riz1999/jenkins_pipeline.git'
            }
        }
        stage('build') {
            steps {
                sh 'sudo apt install -f maven'
                sh 'sudo mvn clean install'
            }
        }
        stage('deploy') {
            steps {
                sh 'sudo cp -v webapp/target/webapp.war /tomcat/webapps/'
            }
        }
    }
}
