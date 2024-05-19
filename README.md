# jenkins_compose
Pipelines and Jenkins test.

1- Running Jenkins With Docker Compose:
    Create a directory named jenkins_compose and create a file named docker-compose.yaml with these contents.

2- Run Jenkins Controller
    Run docker-compose in the directory where you placed docker-compose.yaml.

    docker-compose up -d

3- Adding a Jenkins Agent With Docker Compose
    Generate an SSH key:
    ssh-keygen -t rsa -f jenkins_agent

    This command creates two files: jenkins_agent, which holds the private key, and jenkins-agent.pub, the public key.

    Login to Jenkinks.
    Start with the Manage Jenkins menu.
    Then go to Manage Credentials.
    Click Jenkins under Stores scoped to Jenkins.
    Click Add Credentials in the menu on the left.
    Set these options on this screen.
        Select SSH Username with private key.
        Limit the scope to System. This means the key can’t be used for jobs.
        Give the credential an ID.
        Provide a description.
        Enter jenkins for a username. Don’t use the username used to create the key.
        Under Private Key,  check Enter directly.
        Click OK to save the credential.

4- Adding Docker to Jenkins image
    Dockerfile to create a Jenkins image with Docker Engine included

5- Run this command for set privilegies:
    docker exec -it --user root jenkins bash
    chown jenkins /var/run/docker.sock    