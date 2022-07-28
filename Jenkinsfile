pipeline
{

   agent 
   {
                                    dockerfile true
   }
    environment {
            HOME = '~/.'
            mode = 'apk'
            LANG = 'en_US.UTF-8'
        }
    options {
         
            disableConcurrentBuilds()
          
        }
    
    stages 
        {   
                    stage('Git Pull and Build Android  Workspace') 
                    {
                              
                        
                        stages  
                            {
                                    
                                stage('Build Gradle Android')
                                {
                                    
                                    steps 
                                        {

                                                
                                                sh 'ls'
                                                sh 'pwd'
                                                
                                                sh './gradlew assembleDebug'
                                                 
                                         }
                                        
                                }
                                    					
                            
                                
                            
                            }   
                        post 
                            {
                                success 
                                { 
                                   
                                    archiveArtifacts artifacts: '**/*.apk', fingerprint: true
                                }
                            }
              
                     }      
        }

   /* post {    
        
        failure 
            {
                //cleanWs()
            }
        success 
            {
                //cleanWs()
            }
        } */
}
