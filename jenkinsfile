pipeline {
    agent any
    environment   {
        name = 'gaurav'
    }
     parameters {
         string(name:'Person', defaultValue:'Deepanshu Sharma ',description:'Who are you?')
         booleanParam(name:'isMale',defaultValue:true,description:'')
         choice(name:'City',choices:['Jaipur','Mumbai','Pune'], description:'')
            }
    stages  {
        stage('test')    {
           steps  {
               sh  '''date
                       ls
                       pwd
                      '''
                      }
            }
         stage('Environment Variable')  {
           steps  {
                sh    'echo ${BUILD_ID}'       
                sh    'echo ${name}'
           }
         }
              stage('Parameters')    {
           steps  {
               echo     "Person"
           }
           }
    
          stage ('Continue ?')   {
              input     {
                     message   "Should we Continue ?"
                     ok  "Yes we should"
              }
    
           steps  {
               echo     "Person"
           }
          }
             stage('deploy  on prod')   {
           steps  {
               echo  "deploy on prod"
           }
             }  
            }
        post { 
        always { 
            echo 'I will always say Hello again!'
        }
         failure { 
            echo 'Failure!'
         }
        success {
            echo 'Success'       
        }

        }
    } 
    
