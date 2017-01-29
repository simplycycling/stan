# StreamCo DevOps Lab

Changed my mind.

I'm doing this a bit differently, now. This is a bit more reflective of how I
would set up an environment like this; building an image with Packer, using
Ansible as a provisioner, and then spinning up the environment with CloudFormation.

Ideally, this would all be done with some type of CI/CD - whenever a commit is
made to the repo, to any part of it, it would trigger a test, of which a pass
would subsequently fire off a Packer run, after which a CloudFormation run
would happen, updating the environment.

One part of this I'm not sure how to do yet - when the Packer run completes,
it outputs the id number of the image that it creates. What I'd like to have
happen would be for the image number to be outputted to a variable, that would
be read by cloudformation, rather than having to manually add it to the CF
stack. 

As it stands, to run this, Packer would be run with the following command:

    packer build -var 'aws_access_key=AKIA...' -var 'aws_secret_key=...' example.json
    
