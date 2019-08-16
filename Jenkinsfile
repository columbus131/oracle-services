
pipeline{
  agent{
    label { label 'itcloudconfig' 
    }
  }
  stages {
      stage ('stopERPApplication'){
      steps{
           echo 'Stopping the Application Services' 
           sh 'sudo cat /etc/redhat-release > release.txt'
           sh 'sudo su bramireddy /home/bramireddy/space.sh '
           sh  'ls -ltr'
           sh 'pwd > present.txt'
      }
      }
      stage ('stopERPDatabase'){
      steps{
           echo 'stopping the Database' 
      }
  }
    stage ('Applying Security Updates '){
      steps{
           echo 'Patching the Database Server'
      }
    }
  }
  post {
    success {
                echo 'Patching Completed'
    }
  }
}
