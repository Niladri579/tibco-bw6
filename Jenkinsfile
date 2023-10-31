pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/Niladri579/tibco-bw6.git']]])
            }
        }

        stage('Build') {
            steps {
                // Set up environment and install BW6 dependencies
                sh '''
                    export BW_HOME=/path/to/tibco/bwce/2.6
                    export PATH=$PATH:$BW_HOME/bin
                '''

                // Build BW6 application
                sh 'cd path/to/BW6-Application && bw installApp -d'
            }
        }
    }
}

