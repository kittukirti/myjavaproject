pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kittukirti/myjavaproject.git']]])
            }
        }
        stage('Build') {
            steps {
                sh '''
                    #!/bin/bash
                     pwd
                    cd /var/lib/jenkins/workspace/MyJavaCI/MyJavaProject
                    echo "Build started"
                    mvn compile
                    echo "Packaging started"
                    mvn package
                    pwd
                '''
            }
        }
    }
}
