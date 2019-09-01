pipeline {
    agent any
    stages {
        stage('Upload to AWS.') {
            steps {
                withAWS(credentials:'aws-static') {
                    s3Upload(file:'index.html', bucket:'jenkins-static-site', path:'./index.html')
                }
            }
        }
        stage('Linting') { 
            steps {
                sh 'tidy -q -e *.html'
            }
        }
    }
}
