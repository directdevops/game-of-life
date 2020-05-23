node {
    stage('scm'){
        git branch: 'master', url: 'https://github.com/dummyrepos/game-of-life.git'
    }
    stage('maven') {
           sh 'echo buildng package'
           sh 'mvn package'
    }
    stage('Sonar') {
        withSonarQubeEnv('SONAR-6.7.4') {
             sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
        }
    }
}
