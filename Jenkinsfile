 pipeline { 
     agent any 
  
     stages { 
  
         stage('Checkout') { 
             steps { 
                 echo 'Source downloaded' 
             } 
         } 
  
         stage('Verify') { 
             steps { 
                 sh 'ls -la' 
             } 
         } 
  
     } 
 }