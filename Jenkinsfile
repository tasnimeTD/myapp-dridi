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

sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "

}
}
}


stage('docker') {
steps{
script {


sh "ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml "


}
}
}

}
}


