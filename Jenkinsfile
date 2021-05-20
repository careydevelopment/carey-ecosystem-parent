pipeline {
    agent any

    tools {
        maven "M3"
    }

    environment { 
        POM_VERSION= sh (returnStdout: true, script: 'mvn org.apache.maven.plugins:maven-help-plugin:3.1.0:evaluate -Dexpression=project.version -q -DforceStdout').trim()
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
