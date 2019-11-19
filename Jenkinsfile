pipeline {
    agent any
    tools { 
        maven 'Maven' 
    }
    stages {
        stage('Build') {
            steps {
                snDevOpsStep()
                snDevOpsChange()
                sh 'mvn clean install -DskipTests=true'
            }
        }
        stage('Unit Test') {
            steps {
                snDevOpsStep()
                sh "mvn test -Dtest=AppTest"
            }
        }
        stage('Integration Test') {
            steps {
                snDevOpsStep()
                echo "Integration Test"
            }
        }
        stage('Deploy') {
            steps {
                snDevOpsStep()
                snDevOpsChange()
                // sh "mvn -B deploy"
                // sh "mvn -B release:prepare"
                // sh "mvn -B release:perform"
                // deploy using kubernetes - kubectl
                 echo "Deploy to prod"
            }
        }
    }
}
