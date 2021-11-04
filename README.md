# build:
on `/app`
`docker build -t cpu_logger_im .`

# run
`docker run -i -w /wd -v ~/Desktop/app:/wd cpu_logger_im`

# Why using docker configuration file?
Even though I saw that it could be a little easier creating an image without the dockerfile,
I used the config file because I needed psutil and I saw it is native on some of the linux machines I tried it on, but not on others.


- timestamp is showing UTC time

- file is created and written to.
