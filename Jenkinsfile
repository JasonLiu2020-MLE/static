pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-east-2',credentials:"aws-static") {
                    s3Upload(file:'index.html', bucket:'jenkins-bucket-s3',path:'./')
                }
            steps {
                sh 'echo "Hello World!"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                    '''
            }
        }
    }

}
