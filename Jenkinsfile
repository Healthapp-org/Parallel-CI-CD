peline{
  agent any
  stages{
  	stage('version-control'){
  		steps{
  			checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'f7c765a1-e95f-44ad-9f53-7b9fc6ad20ec', url: 'https://github.com/Healthapp-org/Parallel-CI-CD.git']]])
  		}
  	}
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'simpletest.sh'
          }
        }
    stage('parallel-job'){
      parallel{
        stage('sub-job2'){
          steps{
            sh 'lscpu'
            sh 'lsblk'
          }
        }
    stage('parallel-job'){
      parallel{
        stage('sub-job3'){
          steps{
            sh 'uptime'
            sh 'ps -ef'
          }
        }        
        stage('sub-job4'){
          steps{
            sh 'bash /var/lib/jenkins/workspace/Parallel Jenkins-CI-CD/system.sh'
          }
        }
      }
    }
    stage('codebuild'){
    	steps{
    		sh 'cat /etc/passwd'
        sh 'ls -l'
    	}
    }
  }
}
