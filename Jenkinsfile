pipeline {
  
  agent any
   
  tools {

     maven 'M3'
      }  
  stages {
         
      stage ('clone the repo') {
           steps {
                  git 'https://github.com/varuntiwari91/spring-petclinic.git'
                }
         }
      stage ('Build') {
           steps {
                  sh 'mvn clean compile'
                }
         }
      stage ('unit test') {
           steps {
                  sh 'mvn test'
                } 
         }
      stage ('package') {
           steps {
                  sh 'mvn package'
                }  
         }
      stage ("Deploy to Production"){
        
            steps {
                    sh "scp /var/lib/jenkins/workspace/mavenpipeline-bv/target/spring-petclinic-2.1.0.BUILD-SNAPSHOT.jar ubuntu@13.233.76.212:/opt/tomcat/webapps"
}

      }
}  
}
