flag = true

pipeline {
     agent any
     environment {
          //variables defined here can be used by any stage
          NEW_VERSION = '1.3.0'
     }
     
     stages {
        stage('Build') {
            steps {
                 echo 'Building..'
// Here you can define commands for your build
                 echo "Building version ${NEW_VERSION}"
            }
        }
       
  stage('Test') {
         steps {
            echo 'Testing..'
// Here you can define commands for your tests
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
