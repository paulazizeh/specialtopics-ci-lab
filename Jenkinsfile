
node {
  stage('checkout sources') {
        // You should change this to be the appropriate thing
        git url: 'https://github.com/paulazizeh/specialtopics-ci-lab'
  }


  stage('Build') {
    // you should build this repo with a maven build step here
    withMaven (maven: 'maven3') {
    sh "mvn package"
    }
    echo "hello"
  }
  try {
          stage('Test') {
              sh 'mvn test'
          }
      } finally {
          junit 'build/reports/**/*.xml'
      }
}
