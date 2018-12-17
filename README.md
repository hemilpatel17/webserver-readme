# Project Title

This project implements a simple web server that tells user their ip address, geolocation and timzone.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

Go is installed on the development and build machines.

### Installing

Download source code into a directory of your choice. We will use ```~``` here on.
```
      cp -r webserver/ ~/webserver
```
You can simply run the application locally by Running
```
      cd ~/webserver
      go run server.go
```
To execute tests, you can run
```
      cd ~/webserver
      go test
```

## Deployment

To deploy this on a live server, you will have to build the app first.
The instructions build for different architecture may vary, the following instructions are for linux.

Download source code into a directory of your choice. We will use ```~```from here on.
```
      cp -r webserver/ ~/webserver/
```
Build the app and create an executable
```
      cd ~/webserver
      env GOOS=linux go build -v -o build/webserver
```
Copy Static files into the build folder
```
      cp ~/webserver/server.html ~/webserver/build/
```
Copy the build folder to your live/remote server
```
      [On your local machine where the executable lives]
      cd ~/webserver
      [there should be an executable here with name 'webserver' previously created]
      scp -r build {user}@{remoteserver}:~

      [On your Remote Server]
      cd ~
```
Run the application
```
      [On your Remote Server]
      cd ~/build
      ./webserver
```
OR

Run the application in the background
```
      [On your Remote Server]
      cd ~/build
      nohup ./webserver > /tmp/server.out 2>&1 &
```

## Built With

* [Go](https://github.com/golang/go) - The framework used


## Authors

* **Hemil Patel** (https://github.com/hemilpatel17) - Created a simple server to show user's their ip, geolocation and timezone

## Acknowledgments

* Thank you to [PurpleBooth](https://github.com/PurpleBooth) for providing the README.md template
