pipeline {
   agent any
   tools {
      maven 'Maven'
   }
   stages {
       stage("build") {
           steps {
              snDevOpsStep '95ac543fdbb7bf40963c5c55dc9619fe'
               echo "Building" 
                sh 'mvn clean install -DskipTests'
               sleep 5
              snDevOpsChange()
           }
       }
       
       stage("test") {
           steps {
               snDevOpsStep '15ac543fdbb7bf40963c5c55dc9619fe'
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
               snDevOpsStep '1dac543fdbb7bf40963c5c55dc9619fd'       
               echo "Deploying"
               // release process
               // release process
               sleep 7
           }
       }
   }
}
