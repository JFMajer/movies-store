def imageName = 'jfmajer/movies-store'

node ('workers') {
    stage('Checkout') {
        checkout scm
    }

    def imageTest = docker.build("${imageName}-test", "-f Dockerfile.test ." )

        stage('Quality Tests') {
            imageTest.inside{
                sh "ls -la"
                sh "pwd"
            }
        }
    stage('Build') {
        docker.build(imageName)
    }
}
