pipeline {
   agent any
   tools {
      maven 'Maven'
   }
   stages {
       stage("build") {
           steps {
              snDevOpsStep ()
              // echo "Building" 
               // sh 'mvn clean install -DskipTests'
              // sleep 5
              snDevOpsChange()
           }
       }
       
       stage("test") {
           steps {
               snDevOpsStep ()
               echo "Testing"
               sh 'mvn test -Dpublish'
               sleep 3
           }
          post {
                always {
                    junit '**/target/surefire-reports/*.xml' 
                }
          }
        }

       stage("deploy") {
           steps {
               snDevOpsStep ()       
               echo "Deploying"
               // release process
               // release process
               sleep 7
           }
       }
   }
}
