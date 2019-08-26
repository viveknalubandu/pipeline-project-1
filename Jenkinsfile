pipeline {
   agent any
   tools {
      maven 'Maven'
   }
   stages {
       stage("build") {
           steps {
              snDevOpsStep '77cf85c10f6333009d1a986eb4767eae'
               echo "Building" 
                sh 'mvn clean install -DskipTests'
               sleep 5
           }
       }
       stage("test") {
           steps {
               snDevOpsStep '7bcf85c10f6333009d1a986eb4767eae'
               echo "Testing"
               sh 'mvn test -Dpublish'
               sleep 3
           }
       }
       stage("deploy") {
           steps {
               snDevOpsStep 'f7cf85c10f6333009d1a986eb4767eae'
               snDevOpsChange()
               echo "Deploying"
               // release process
               // release process
               sleep 7
           }
       }
   }
}
