try{
    node {
    echo 'Build Started'
    stage('Checkout'){
         git branch: 'master', credentialsId: 'bitbucket', url: 'https://github.com/Madan2488/Ant-WebProject.git'
    }
   
        stage('build'){
        bat 'ant -f build-mt.xml'
    }
     stage('Test'){
      /*  sh 'mvn test' */
         echo 'test done'
    }
    stage('Package'){
       /* sh 'mvn package' */
        echo 'Package done'
    }
    stage('Deploy-dev'){
        echo 'Deployed to dev'
    }
    stage('Deploy-stg'){
        echo 'Deployed to stg'
    }
    stage('Deploy-prod'){
        echo 'Deployed to prod'
    }
    stage('Deploy-to-Tomcat'){
        bat 'cp target/*.war D:\DevOPs\softwares\apache-tomcat-8.5.32-windows-x64\apache-tomcat-8.5.32\webapps'
    }
    stage('Email'){
     body_msg = ''' Jenkins Job success 
   
    '''+"$JOB_URL"+''' 
    Thanks
    Jenkins
    '''
   mail bcc: '', body: body_msg, cc: '', from: '', replyTo: '', subject: 'Job Success', to: 'madan5.ctr@gmail.com'
   
    }
  }
}catch(error){
   echo 'Some error occured, Please verify' 
   throw error
}
