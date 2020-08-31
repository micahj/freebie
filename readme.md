## docker build and run

On your dev machine

    cd docker
    docker build -t freebie:v1 .
    cd ..
    docker run -it -v $(pwd)/conf:/etc/freeswitch freebie:v1

## register zoiper softphone

You need the freeswitch IP so at the command line call a docker ps and get the container uuid
then docker inspect that and check the container ip

    docker ps
    ... running container ids.... then
    docker inspect the-freeswitch-containers-uniqueid-here

Chances are the container will be running at 172.17.0.2 or there abouts

In zoiper (or your favourite softphone desktop app) register an account, for example account 1000.
You can supply the user account info to zoiper like so
eg
1000@172.17.0.2:5060 and step through the prompts.
The password in our case is 12345! (see vars.xml). No sensitive intellectual property there so fear not.

## some test calls

Note the call connection may take a few seconds to play in each case.

### speak back the extension you called from

dial 1500

### play a very robotic sounding development only tts prompt.

dial 9886

### play a small ivr and select from options

dial 5002: Once prompted use the calls embedded dialpad and press 5 for hours of fun
