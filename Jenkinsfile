flag = true

pipeline {
     agent any
      parameters {
                string(name: 'VERSION',defaultValue:'',description:'version to deploy on prod')
                choice (name:'VERSION',choices:['1.1.0','1.2.0','1.3.0'],description:'')
                booleanParam(name:'executeTests',defaultValue: true, description:'')
      }
     
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
         when{
              expression {
                        params.executeTests
              }
         }
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
