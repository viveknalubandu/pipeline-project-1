pipeline {
   agent any
   tools {
      maven 'Maven'
   }
   stages {
       stage("build") {
           steps {
              snDevOpsStep '456e9d150f6333009d1a986eb4767e83'
               echo "Building" 
                sh 'mvn clean install -DskipTests'
               sleep 5
           }
       }
       stage("test") {
           steps {
               snDevOpsStep '496e9d150f6333009d1a986eb4767e83'
               echo "Testing"
               sh 'mvn test -Dpublish'
               sleep 3
           }
       }
       stage("deploy") {
           steps {
               snDevOpsStep 'c56e9d150f6333009d1a986eb4767e83'
               snDevOpsChange()
               echo "Deploying"
               // release process
               // release process
               sleep 7
           }
       }
   }
}
