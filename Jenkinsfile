pipeline {
    agent any
    
    stages {
        // Step 1
        stage('SCM') {
                steps {
                    git 'https://github.com/webdevprashant/jenkins-training-CI-CD-Day6.git'
                }        
        }
        // Step 2
        stage('Build by Maven') {
                steps {
                    sh '/var/lib/jenkins/apache-maven-3.6.3/bin/mvn clean package'
                }
        }
        
        // Step 3
        stage('Build docker image') {
                steps {
                    sh " docker build -t rachanad10/javaapp:${BUILD_NUMBER} ."
                }
        }
        
        // // Step 4
        // stage('Push docker image') {
        //         steps {
        //             withCredentials([string(credentialsId: 'Docker_hub_password', variable: 'VAR_FOR_DOCKERPASS')]) {
        //             sh " docker login -u webdevprashant -p $VAR_FOR_DOCKERPASS"
        //             }
        //             sh " docker push webdevprashant/javaapp-day6:${BUILD_NUMBER}"
        //         }
        // } 
        
        // // Step 5 
        // stage('Deploy Java App in  Dev Env') {
        //         steps {
        //                 sh " docker rm -f javaapp"
        //                 sh " docker run  -itd --name javaapp -p 1222:8080 rachanad10/javaapp:${BUILD_NUMBER}"
        //         }
        // }
        
        // // Step 6  in  Redhat CLI 1 
        // stage('Deploy Java in QA/Test Env') {
        //     steps {
        //             // sshagent(['QA_ENV_SSH_CRED']) {
        //                 // sh "ssh root@192.168.43.229 docker rm -f myjavaapp"
        //                 // sh "ssh root@192.168.43.229 docker run  -d -p 8080:8080 --name myjavaapp webdevprashant/javaapp-day6:${BUILD_NUMBER}"
        //     sh " docker rm -f myjavaappqatestenv"            
        //     sh " docker run  -d -p 1223:8080 --name myjavaappqatestenv webdevprashant/javaapp-day6:${BUILD_NUMBER}"           
        //             // }
        //     }
        // }
            
        // stage('QAT Test') {
        //     steps {
        // 	// bcz tomcat take some sec. to display data , so apply some delay here        
        //         retry(30) {
        //             sh 'curl --silent http://192.168.43.56:1223/java-web-app/ |  grep India'
        //         }   
        //     }
        // }
        
        // // Step  in Redhat 8 CLI 2
        // stage('Deploy webAPP in Prod Env') {
        //     steps {
               
        //     //   sshagent(['QA_ENV_SSH_CRED']) {                    
        //                 // sh "ssh root@192.168.43.229 docker rm -f myjavaapp"
        //                 // sh "ssh root@192.168.43.229 docker run  -d -p 8080:8080 --name myjavaapp webdevprashant/javaapp-day6:${BUILD_NUMBER}"                   
        //         // }
        //         sh " docker rm -f myjavaappprodenv"
        //         sh " docker run  -d -p 1224:8080 --name myjavaappprodenv webdevprashant/javaapp-day6:${BUILD_NUMBER}"  
        //     } 
        // }
    }
}      
