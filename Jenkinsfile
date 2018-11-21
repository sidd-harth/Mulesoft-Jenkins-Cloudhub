pipeline{
 agent any
 environment {
    ANYPOINT = credentials('mulesoft-anypoint-platform')
 }
 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven:'mvn'){
 				sh 'mvn -f mule-jenkins-pipeline/pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven:'mvn'){
 				sh 'mvn -f Mulesoft-Jenkins-Cloudhub/pom.xml package deploy  -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Development -DmuleDeploy'
 			}
 		}
 	}
 }

}