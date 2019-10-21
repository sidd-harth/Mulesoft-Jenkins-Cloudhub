pipeline{
 agent any
 tools {
        maven 'M2'
        jdk 'JDK'
        nodejs 'NODEJS'
    }

 stages {
   stage('Check Parameters') {
   steps {
    echo "Production App Name - ${username}"
    echo "Application Name - ${password}"

   }
  }
 	stage ('Build'){
 		steps {
 		
 				bat 'mvn -f pom.xml clean install'
 		
 		}
 	}
 	stage ('Deploy'){
 		steps {
 		
 				bat 'mvn -f pom.xml package deploy  -Dusername=mule-7 -Dpassword=Qwerty67 -DmuleDeploy'
 		
 		}
 	}
 }

}
