## build:
on `/app`  preform `docker build -t cpu_logger_im .`  
`-t cpu_logger_im`  create a tag for the image  


## run
`docker run -i -w /wd -v ~/Desktop/app:/wd cpu_logger_im`  
`docker run -i -w /wd -v <external to docker> : <internal> <image tag name>`  
`-i` interactive   i/o to terminal

## Why using docker configuration file?
Even though I saw that it could be a little easier creating an image without the dockerfile,
I used the config file because I needed psutil and I saw it is native on some of the linux machines I tried it on, but not on others.

- timestamp is showing UTC time


## Docker file properties:
ADD- copying cpu_log.py to current dir.  
RUN- install psutil library because the script is using it.  
CMD- what needs to be written in the command line to run the script.  


## Why opening and closing the output file on every access?
The program opens and closes the file on each access to ensure that if the program  crashes in the middle of the running, then the file is valid and only the last access is lost. 
It is a better practice than holding file "in the air", taking up resources. 
On other circumstances, like much higher frequency, we might require another solution.

