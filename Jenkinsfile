pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-west-2', credentials:'078563032339') {
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins-vivz')
            }
        }
    }
  }
}