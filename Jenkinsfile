pipeline {
   agent any

   stages {
      stage('Hello') {
         steps {
            echo 'Hello World'
         }
      }
      
      stage('Docker build')
      {
          steps{
              script{
                  docker.build('rohan-aws-pro')
              }
          }
      }
      
      stage('Push docker'){
          steps{
              script{
                docker.withRegistry('https://186319575019.dkr.ecr.us-east-2.amazonaws.com/rohan-aws-pro', 'ecr:us-east-2:myaws_accessid') {
                        docker.image('rohan-aws-pro').push('latest')
                        //def customImage = docker.build("nginx:${env.BUILD_ID}")
                        //customImage.push()
                    }
                }
          }

          }
      }
   }
