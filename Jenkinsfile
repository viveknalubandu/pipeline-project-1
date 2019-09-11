pipeline {
   agent any
   tools {
      maven 'Maven'
   }
   stages {
       stage("build") {
           steps {
              snDevOpsStep 'd56177ca0fb333009d1a986eb4767e53'
               echo "Building" 
                sh 'mvn clean install -DskipTests'
               sleep 5
           }
       }
       
       stage("test") {
           steps {
               snDevOpsStep 'dd6177ca0fb333009d1a986eb4767e52'
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
               snDevOpsStep '556177ca0fb333009d1a986eb4767e53'
               snDevOpsChange()
               echo "Deploying"
               // release process
               // release process
               sleep 7
           }
       }
   }
}
