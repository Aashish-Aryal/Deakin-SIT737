## Week 2

Step 1: Install nodejs
`sudo apt install nodejs`

Step 2: Install Express
Create a new directory named 'Week-2'
Run the following command:
`npm init`
`npm install express`

### server.js
A simple code which imports express and connects to port 3000 of localhost.

### server_get.js
This code has a function which take 2 numbers as the input and returns theirs sum. This code also has a express app which listens to port 3040 of localhost, from where we can send a get request with 2 numbers to get their sum. 

We got the package.json file from out tutor. Here the `start` script is configured to run the server_get.json code. 

* Run the command `npm start` to start the server_get.json.
* login to (http://localhost:3040/addTwoNumber?n1=5&n2=7) in your browser to send a get request with n1=5 and n2=7 as parameters. Then the app will return the sum.