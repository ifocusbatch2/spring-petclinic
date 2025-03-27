pipeline{

    agent any

    stages{

       stage('clone the project'){
        steps{
            
           git branch: 'master', url: 'https://github.com/ifocusbatch2/spring-petclinic.git'
          
        }

       }

       stage('Build the project'){
        steps{
           sh 'mvn clean install'
        }

       }

       stage('Test'){
        steps{
           sh 'mvn test'
        }

       }
       stage('published the test results'){
        steps{
           junit 'target/surefire-reports/*.xml'
        }

       }
       stage('publishedd the artifacts'){
        steps{
           archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
        }

       }

    }
}