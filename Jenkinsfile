pipeline {
  agent any 
  stages {
    stage('Lint HTML.'){
        steps {
            sh "tidy -q -e *.html"
                  }
            }

    stage('Upload to AWS.') {
        steps {
            withAWS(region:'ap-south-1',credentials:"aws-static") {
            s3Upload(file:'index.html', bucket:'s3-bucket-jenkins', path:'index.html')
                    }
            }
        }
    }
}