Requirements

    CI/CD with Jenkins

Instructions

[ CI/CD ]

    Using Jenkins, create a pipeline running:
        Repository pull
        Image build
        Testing Your Code
        Push Image into your own docker registry private
        SSH into your server
        Pull image from docker registry private
        Redeploy your deployment apps
    For testing Stage, you must use sonarqube for testing your code quality
        Sonarqube
            On your cicd workflow, use sonarqube for testing your quality code.
            You can use others testing tools like trivy for scanning your images or some.
            And try test your running app by using wget spider
JAWABAN:

