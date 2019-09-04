pipeline {
   agent any
   tools {
      maven 'Maven'
   }
   stages {
       stage("build") {
           steps {
              snDevOpsStep (stepSysId:'de251af7db2bb340bffe5223dc9619c2', disabled:true, ignoreFailure: true)
               echo "Building" 
                sh 'mvn clean install -DskipTests'
               sleep 5
           }
       }
       
       stage("test") {
           steps {
               snDevOpsStep (stepSysId:'52251af7db2bb340bffe5223dc9619c3', disabled:true, ignoreFailure: true)
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
               snDevOpsStep (stepSysId:'d2251af7db2bb340bffe5223dc9619c3', disabled:true, ignoreFailure: true)
               snDevOpsChange(ignoreFailure:true, disabled:false)
               echo "Deploying"
               // release process
               // release process
               sleep 7
           }
       }
   }
}
