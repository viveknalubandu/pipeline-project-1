pipeline {
   agent any
   tools {
      maven 'Maven'
   }
   stages {
       stage("build") {
           steps {
              snDevOpsStep '6ba30d92db23ff00bffe5223dc9619fe'
               echo "Building" 
                sh 'mvn clean install -DskipTests'
               sleep 5
           }
       }
       
       stage("test") {
           steps {
               snDevOpsStep '67a30d92db23ff00bffe5223dc9619fe'
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
               snDevOpsStep 'e7a30d92db23ff00bffe5223dc9619fe'
               snDevOpsChange()
               echo "Deploying"
               // release process
               // release process
               sleep 7
           }
       }
   }
}
