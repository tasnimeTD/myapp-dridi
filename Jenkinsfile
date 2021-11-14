pipeline
{

agent any
 stages {
  
   stage('PULL') {

   steps {
   
   script {

checkout([$class: 'GitSCM', branches: [[name: '*/master']],

userRemoteConfigs: [[
url: 'https://github.com/medchaib/myapp-chaib.git' ]]])



}
}
}

stage('build') {
steps{

script {

sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "

}
}
}

}
}


