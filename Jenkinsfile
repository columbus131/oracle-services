
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
           sh 'sudo init 6'
      }
  }
    stage ('Applying Security Updates '){
      steps{
           echo 'Patching the Database Server'
           //sh 'sudo yum update --security --assumeno'
           sh 'sudo cat  /var/log/yum.log'
      }
    }
  }
  post {
    success {
                echo 'Patching Completed'
           mail to: 'bramireddy@idirect.net',
             subject: "Patching Success : ${currentBuild.fullDisplayName}",
             body: "Patching Completed on ERP Application  ${env.BUILD_URL}/consoleText"
    }
     failure {
        mail to: 'bramireddy@idirect.net',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Patching Failed for some reason  ${env.BUILD_URL}"
    }
  }
}
