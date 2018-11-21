pipeline 
{
    agent any    
    tools
    {
        maven 'System_Maven'
        jdk 'System_MAC_JDK'
    }
          
      stages
      {
        stage('Init')
        {
          steps
          {
          echo "Testing..."         
        }     
      }
        stage('Build')
        {
        steps
          {
            echo "Building..."         
          }     
      }
        stage('Deploy')
        {
          steps
          {
            echo "Code Deployed..."         
        }     
      }
   }
}
