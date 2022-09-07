pipeline{
  agent any
  stages{
    stage('git-clone'){
          steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/team3Group2EtechApp/etechAppMulti-Pipeline.git']]])
      }
    }
      stage('1-first parallel job'){
        when {
          branch 'develop'
        }
        parallel{
        stage('Phil-action'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/phil.sh'
          }
        }
        stage('abisola'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/abisola.sh'
          }
        }
      }
    }
        stage('2nd parallel job'){          
        parallel{
        stage('Anthony-actions'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/anthony.sh'
          }
        }
       stage('Judith-actions'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/judith.sh'
          }
        }
      }
    }
    stage('3rd parallel job'){
      when {
        branch 'feature'
      }
        parallel{
        stage('Monic-action'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/monic.sh'
          }
        }
       stage('engineer-felix'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/felix.sh'
          }
        }
      }
    }
    stage('4th parallel job'){
        parallel{
        stage('Christiane-action'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/christiane.sh'
          }
        }
       stage('engineer-Ntizeah'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/ntizeah.sh'
          }
        }
      }
    }
  }
}
       