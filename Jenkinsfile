pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-west-2',credentials:"AKIAWNM2NMQZHTUNCQGL") {
                    s3Upload(file:'index.html', bucket:'jenkins-bucket-s3', path:'index.html')
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
