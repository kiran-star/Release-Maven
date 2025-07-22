pipeline {
    agent {
        label 'LabelSlave'
    }
    options{
        disableConcurrentBuilds()
    }
    environment{
        WRS = '/home/jenkins/jenkins-agent/workspace/Pipeline-Project'
    }
    stages{
        stage('Preparation-Stage'){
            parallel{
                /*
                   stage('Preparation'){
                    agent {
                        label 'LabelSlave'
                    }
                    steps{
                        dir("$WRS"){
                        echo "Cloning Git Repo"
                        git 'https://github.com/kiran-star/Release-Maven.git'
                        echo 'Git-Webhook'
                        sh """
                        pwd
                        ls
                        ls -ltr
                        """
                        }
                    }
                }
                */
                stage('Perform'){
                    agent{
                        label 'LabelSlave'
                    }
                    steps{
                        // mvn clean package
                        //java -jar /home/jenkins/jenkins-agent/workspace/Parallel-Proj/target/first-demo-jar-1.0.jar
                        dir("$WRS"){
                        sh """
                        mvn clean package
                        pwd
                        ls
                        ls -ltr
                        """
                        echo 'Jenkins Multibranch Pipeline'
                        }
                    }
                }
            }
        }    
    }
}
