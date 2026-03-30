pipeline{
    agent any
    stages{
        stage('1. Checkout'){
                git url:'https://github.com/Abhishek-Chincholikar/docker-git-jenkins.git'
            }
        }

    stage('2. Build Image'){
      steps{
       bat 'docker build -t myweb .' 
        }
    }

    stage('3. Stop all Containers'){
      step{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
        }
    } 

  stage('4.Run the image- Containerize){
      steps{
      bat 'docker run -d -p 8000:80 --name mycont myweb'
        }
    }
}
