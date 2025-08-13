pipeline{
agent any
  tools{
     maven 'mymaven'
  }

stages{
stage('clone Repo')
  {
    steps{
       git 'https://github.com/kamran761/DevOpsCodeDemo.git'     
    }
  }
stage('Build Code')
  {
    steps{
       sh 'mvn package'   
    }
  }

stage('Deploy Code')
  {
    steps{
      deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatdetails', path: '', url: 'http://18.208.109.67:9090/')], contextPath: null, war: '**/*.war'
    }
  }
}
  
}
