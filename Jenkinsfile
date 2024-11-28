flag=true

pipeline {
     agent any
     stages {
        stage('Build') {
            steps {
               echo 'Building..'
// Here you can define commands for your build
            }
        }
       
  stage('Test') {
         steps {
               when {
                    expression {
                              flag ==false
                    }
            echo 'Testing..'
// Here you can define commands for your tests
          }
   }
}

  stage('Deploy') {
          steps {
            echo 'Deploying....'
// Here you can define commands for your deployment
          }
    }

}

    post {
      // the conditions here will execute after the build is done

      always {
            // this action will happen always regardless of teh result of the build
           echo 'Post build condition running'
             }
      
      failure {
           echo 'Post Action if Build Failed'
               }
    }
        
 
  }
