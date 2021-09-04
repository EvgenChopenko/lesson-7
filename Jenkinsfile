node {
  stage 'Build image' 
  git 'https://github.com/EvgenChopenko/lesson-7.git' 
  def myEnv = docker.build 'my-image'
  stage 'Test image'
    myEnv.withRun {c ->
    sh 'ls'
    }
}