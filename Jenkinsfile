pipeline{
 agent any
 environment {
    ANYPOINT = credentials('mulesoft-anypoint-platform')
 }
 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven: 'apache-maven-3.3.9'){
 				bat 'mvn -f pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven: 'apache-maven-3.3.9'){
 				bat 'mvn -f pom.xml package deploy  -Dusername=${username} -Dpassword=${password} -DmuleDeploy'
 			}
 		}
 	}
 }

}