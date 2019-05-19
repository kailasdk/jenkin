pipeline
{
    agent any
    stages
    {
        stage('Compile Stage')
        {
            steps
            {
                withMaven(maven : 'MVN_3.61')
                {
                    sh 'mvn clean install'
                }
            }
        }
        stage('Testing Stage')
        {
            steps
            {
                withMaven(maven : 'MVN_3.61')
                {
                    sh 'mvn test'
                }
            }
        }
        stage('Deploy')
        {
            steps
            {
               sh 'scp -r /root/.jenkins/workspace/dec_pipeline/in28minutes-web-servlet-jsp/target/*.war root@172.31.2.123:/opt/apache-tomcat-8.5.40/webapps'
        }
        }
    }
}
