## Transwrap container server instructions

The backend transwrap server (transwrap.js) is a simple socket server that receives a socket connection data in webm and transwrap / proxies the content to RTMP.


## Here's a simplified version of the instructions for the transwrap container server:

## The transwrap server is responsible for receiving webm socket connections and proxying the content to RTMP. Here are the general instructions for running it:

## 1. Running in a local environment (localhost HTTP): 
- Install the dependencies by navigating to the backend directory and running: 

```
    cd backend/
    npm install
    npm start-test transwrap_local.js
```

#  This should start the server and display the message: 
"Listening on port: 3004".

### 2. Running in HTTPS: 
- The frontend application requires HTTPS, so the transwrap server needs to be set up with the HTTPS module in Node.js. 
- To run the server with HTTPS, you'll need to create or install an SSL certificate. 
- The instructions below will generate self-signed certificates (not recommended for non-development environments): 
- Create the key.pem and cert.pem self-signed certificates for the server. 
## Note: If this is not for development, it is advisable to use AWS Certificate Manager for managing public and private SSL/TLS certificates.

#### Generating certificate for develoment tests locally in HTTPS

```
cd backend/
openssl genrsa -out key.pem
openssl req -new -key key.pem -out csr.pem
openssl x509 -req -days 9999 -in csr.pem -signkey key.pem -out cert.pem
rm csr.pem
```

Running locally in HTTPS

```
npm run startDevs
```

The certificates has to be generated in the backend folder.

**Note:** For Practice purpose only.
Open it on your web browser type https://127.0.0.1:3004 and accept the self signed certificate and get small self sign SSL error.

## [Return to Frontend Deployment](../frontend/README.md)

To allow localhost on ssl, you can paste this line in the address bar and proceed to allow localhost, instructions for 
**chrome only**. 

```chrome://flags/#allow-insecure-localhost```

:warning: **Note:** For test purpose only. remember to restore this configuration after you finish your tests.

-------
Note: This project uses FFMPEG 
please check lisencing aspects.  
FFmpeg is licensed under the GNU Lesser General Public License (LGPL) version 2.1 or later. 
However, FFmpeg incorporates several optional parts and optimizations that are covered by the GNU General Public License (GPL) version 2 or later. 
If those parts get used the GPL applies to all of FFmpeg.