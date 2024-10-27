pipeline {
    agent any

    stages {
        stage('Cloning Git Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/R0d26/jk-public-gh.git'
            }
        }
        stage('Buildig Image') {
            steps {
                sh 'docker build -t webapp:${BUILD_NUMBER} .'
            }
        }
    }
    
        stage('Deploying Application') {
            steps {
                sh '''
                //docker stop webapp_ctr
                docker run --rm -d -p 3000:3000 --name webapp_ctr webapp:${BUILD_NUMBER}'
                ...
            }
        }
    }



