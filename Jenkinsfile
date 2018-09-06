node { 
    
     stage ('git checkout ') {
     checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
    doGenerateSubmoduleConfigurations: false, 
    extensions: [], 
    submoduleCfg: [],
    userRemoteConfigs: [[url: 'https://github.com/suhassgit/hello.git']]])
}
stage (' build app') {
sh 'mvn clean package'

}
stage ('archive artufacts') { 
archiveArtifacts 'target/Helloworldwebapp.war'
stage ('çopy' ) { 
sh 'cp target/Helloworldwebapp.war /opt/apache-tomcat-8.5.33/webapps/'
mail bcc: '',
 body: 'This is test jenkins ', cc: '',
  from: '', replyTo: '',
  subject: 'finished job ',
 to: 'sshejwal@gmail.com'
}
}
}
