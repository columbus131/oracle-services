pipeline{
  agent{
    label { label 'itcloudconfig' 
    }
  }
  stages {
      stage ('stopERPApplication'){
      steps{
           echo 'Stopping the Application Services' 
           sh 'sudo cat /etc/redhat-release > relase.txt'
           sh  'sudo su'
           sh 'pwd > present.txt'
      }
      }
      stage ('stopERPDatabase'){
      steps{
           echo 'stopping the Database' 
      }
  }
  }
}
