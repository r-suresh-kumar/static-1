pipeline {
  agent any 
  stages {
    stage(‘Build’) {
      steps {
        sh ‘echo “Hello World”’
        sh ‘“
                  echo “Multiline shell steps works too”
                  ls -lah
               “‘
      }
    }
  
    stage('Upload to AWS') {
        steps {
            retry(3){
            withAWS(region:'ap-south-1', credentials:'aws-static'){
            s3Upload(file:'index.html', bucket:'s3-bucket-jenkins', path:'')
                    }                             
                }
            }
    }
}
}