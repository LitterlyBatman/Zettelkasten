```
    <!DOCTYPE html>

    <html lang="en">

    <head>

        <meta charset="UTF-8">

        <meta name="viewport" content="width=, initial-scale=1.0">

        <link rel="stylesheet" href="Bliep.css">

        <script src="login.js"></script>

        <script src="cordova.js"></script>

        <script src="google-services.json"></script>

        <title>Bliep!</title>

    </head>

    <style>

        /* Extra small devices (phones, 600px and down) */

@media only screen and (max-width: 600px) {  

  :root{

      --primary-color: crimson;

      --secondary-color: #fff;

      --main-font-size: 12px;

      --secondary-font-size: 8px;

      --corner: border-radius 6px;

  }

  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600&display=swap');

  *{

     font-family: 'Poppins', sans-serif;

     margin:0; padding:0;

     box-sizing: border-box;

     outline: none; border:none;

     text-decoration: none;

  }

  

  .LoginForm{

   position: fixed;

  }

  

  .form-container{

     min-height: 100vh;

     display: flex;

     align-items: center;

     justify-content: center;

     padding:20px;

     padding-bottom: 60px;

     background: #fff7f3;

  }

  .form-container form{

    padding: 16px;

    border-radius: 5px;

    text-align: center;

    width: 339px;

    position: absolute;

    top: 16%;

  }

  .form-container form h3{

     font-size: 20px;

     margin-bottom: 10px;

     color:#333;

     position: relative;

     left: -33.5%;

  }

  .form-container form input{

     width: 100%;

     padding: 12px 15px;

     font-size: 17px;

     margin: 20px 0px;

     background: #f6e7da;

     border-radius: 2px;

     border: solid 2px #0000000d;

  }

  .form-container form .form-btn{

     background: #ffdbc0;

     color: #d95100;

     text-transform: capitalize;

     font-size: 20px;

     cursor: pointer;

   }

   .form-container form .form-btn:hover{

      background: #d95100;

      color: #ffdbc0;

   }

  .form-container form p{

     margin-top: 10px;

     font-size: 20px;

     color:#333;

  }

  

  .LogoImage{

    width: 60%;

    position: absolute;

    top: -9px;

    left: -12px;

  }

  
  

  .circle1 {

     height: 250px;

     width: 250px;

     background-color: #ff9251;

     border-radius: 50%;

     position: fixed;

     top: -14%;

     left: 58%;

   }

  

   .circle2 {

     height: 350px;

     width: 350px;

     background-color: #ff9251;

     border-radius: 50%;

     position: fixed;

     top: 76%;

     left: -32%;

   }

  

   .flex-div{

     display: flex;

     flex-direction: row;

     justify-content: space-between;

     align-items: center;

   }

  

   .labeled{

     position: absolute;

     left: -19%;

     display: block ruby;

     width: 100%;

   }

  

   .checkbox{

     position: fixed;

     left: -40%;

   }

  

   .Forgot_Password{

     display: block ruby;

     position: fixed;

     left: 55%;

     color: #d95100;

   }

  

   .DevLoginButton{

     position: fixed;

     top: 62%;

     left: 43%;

   }

  

   .circle3 {

    width: 275px;

    height: 275px;

    border: 26px solid transparent;

    border-radius: 50%;

    box-sizing: border-box;

    position: relative;

    /*! left: 10%; */

    /*! align-self: center; */

    margin-left: auto;

    margin-right: auto;

  }

  .circle3::before {

    content: "";

    position: absolute;

    bottom: -25px;

    left: 50%;

    transform: translateX(-50%);

    width: 137px;

    height: 50px;

    background-color: #eee;

  }

  

  .AttendanceSpan{

    position: absolute;

    top: 35%;

    font-size: 83px;

    left: 50%;

    transform: translate(-50%, -50%);

    z-index: 1;

    color: #484848;

  }

  

  .HourAmount{

    position: absolute;

    top: 41%;

    font-size: 20px;

    left: 50%;

    transform: translate(-50%, -50%);

    z-index: 1;

    color: #484848;

  }

  .buzztest{

    position: absolute;

    top: 90%;

  }

  .alerttest{

    position: absolute;

    top: 93%;

  }

  

  .progresscircle{

    width: 275px;

    height: 274px;

    border-radius: 50%;

    position: relative;

    top: -11.5%;

    left: -11.5%;

    rotate: 180deg;

  }

  

  .progresscircle::before {

    content: "";

    position: absolute;

    top: 0px;

    left: 49.6%;

    transform: translateX(-50%);

    width: 95px;

    border-left: 32px solid transparent;

    border-right: 32px solid transparent;

    border-top: 53px solid #eee;

}

  

  .progresscircle::after {

    content: "";

    position: absolute;

    top: 50%;

    left: 50%;

    transform: translate(-50%, -50%);

    width: 73%;

    height: 74%;

    border-radius: 50%;

    background: #eee;

  }

  

}

  

/* Small devices (portrait tablets and large phones, 600px and up) */

@media only screen and (min-width: 600px) {  

  

}

  

/* Medium devices (landscape tablets, 768px and up) */

@media only screen and (min-width: 768px) {  

  

  /* Your CSS Code for this device size */    

  

}

  

/* Large devices (laptops/desktops, 992px and up) */

@media only screen and (min-width: 992px) {  

  

  /* Your CSS Code for this device size */    

  

}      

  

/* Extra large devices (large laptops and desktops, 1200px and up) */

@media only screen and (min-width: 1200px) {

  

  /* Your CSS Code for this device size */

  

}

  

/* According to Mobile Orientation */

@media only screen and (orientation: landscape) {  

 :root{

    --primary-color: crimson;

    --secondary-color: #fff;

    --main-font-size: 12px;

    --secondary-font-size: 8px;

    --corner: border-radius 6px;

}

  

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600&display=swap');

  

*{

   font-family: 'Poppins', sans-serif;

   margin:0; padding:0;

   box-sizing: border-box;

   outline: none; border:none;

   text-decoration: none;

}

  

.LoginForm{

   position: fixed;

}

  

.form-container{

   min-height: 100vh;

   display: flex;

   align-items: center;

   justify-content: center;

   padding:20px;

   padding-bottom: 60px;

   background: #fff7f3;

}

  

.form-container form{

   padding: 16px;

   border-radius: 5px;

   text-align: center;

   width: 340px;

   position: absolute;

   top: 7%;

   height: 80%;

}

  

.form-container form h3{

   font-size: 20px;

   margin-bottom: 10px;

   color:#333;

   position: relative;

   left: -33.5%;

}

  

.form-container form input{

   width: 100%;

   padding:10px 15px;

   font-size: 17px;

   margin:8px 0;

   background: #fff3ed;

   border-radius: 5px;

   border: solid 2px #0000000d;

}

  

.form-container form .form-btn{

  background: #ffdbc0;

  color: #d95100;

  text-transform: capitalize;

  font-size: 20px;

  cursor: pointer;

}

  

.form-container form .form-btn:hover{

   background: #d95100;

   color: #ffdbc0;

}

  

.form-container form p{

   margin-top: 10px;

   font-size: 10px;

   color: #333;

}

  

.LogoImage{

  width: 33%;

  position: absolute;

  top: -9px;

  left: -12px;

}

  

.home-container{

  min-height: 100vh;

  display: flex;

  align-items: center;

  justify-content: center;

  padding:20px;

  padding-bottom: 60px;

  background: #eee;

}

  

.circle1 {

  height: 250px;

  width: 250px;

  background-color: #ff9251;

  border-radius: 50%;

  position: fixed;

  top: -25%;

  left: 78%;

}

  

.circle2 {

  height: 350px;

  width: 350px;

  background-color: #ff9251;

  border-radius: 50%;

  position: fixed;

  top: 63%;

  left: -19%;

}

  

.flex-div{

  display: flex;

  flex-direction: row;

  justify-content: space-between;

  align-items: center;

}

  

.labeled{

  position: relative;

  left: -12%;

  display: block ruby;

}

  

.checkbox{

  position: relative;

  left: -7%;

}

  

.Forgot_Password{

  display: block ruby;

  color: #d95100;

}

  

.DevLoginButton{

  position: fixed;

  top: 83%;

  left: 47%;

}

}

    </style>

    <body>

        <div id="page-login" style="display: block;">

            <div class="form-container">

                <img class="LogoImage" src="img/InspaLogo.png" alt="">

                <div class="circle1"></div>

                <div class="circle2"></div>

                <form class="LoginForm" id="loginForm">

                    <p id="Login-Fault" style="color: red; display: none;">Incorrect username or password.</p>

                    <p id="Login-Error" style="color: red; display: none;">LOGIN API is currently offline.</p>

                    <h3>Login Now</h3>

                    <input id="username" type="Username" required placeholder="enter your Username">

                    <input id="password" type="password" required placeholder="enter your Password">

                    <div class="flex-div">

                        <input class="checkbox" type="checkbox" id="Remember" name="Remember"/>

                        <label class="labeled" for="Remember">Remember me?</label>

                        <a class="Forgot_Password" href="#">Forgot password?</a>

                    </div>

                    <input  type="button" onclick="submitLoginForm()" value="login now" class="form-btn">

                    <p>Dont have an account? Ask your IT team for access and get an account now!</p>

                </form>

                <button class="DevLoginButton" onclick="DevLogin()">test login</button>

                <button class="buzztest" onclick="Buzztest()">Buzz</button>

                <button class="alerttest" onclick="AlertTest()">Alert</button>

            </div>

        </div>

  

        <div class="home-container" id="page-home" style="display: none;">

            <p>Welcome, <span id="username-display"></span>!</p>

            <p>Your serial number is: <span id="serial-display"></span></p>

            <span class="AttendanceSpan" id="attendance-display">999</span>

            <p class="HourAmount">uur present</p>

            <p id="Info-Fault" style="color: red; display: none;">Serial number not found.</p>

            <p id="Info-Error" style="color: red; display: none;">TIME API is currently offline.</p>

            <button onclick="logoutUser()">logout</button>

            <div class="circle3"><div class="progresscircle" style="background-image: conic-gradient( pink 0deg, lightblue 0 29deg, orange 0deg );"></div></div>

            <button onclick="animateProgressCircle(29, 331, 500);">fill bar</button>

            <span id="CheckInStatus"></span>

            <button onclick="navigateTo('profile');">profile page</button>

            <button onclick="navigateTo('absenceForm');">afwezig melden page</button>

            <button onclick="navigateTo('settings');">settings</button>

            <button onclick="navigateTo('home');">home</button>

        </div>

  

        <div id="page-profile" style="display: none;">

            <button onclick="navigateTo('profile');">profile page</button>

            <button onclick="navigateTo('absenceForm');">afwezig melden page</button>

            <button onclick="navigateTo('settings');">settings</button>

            <button onclick="navigateTo('home');">home</button>

        </div>

  

        <div id="page-settings" style="display: none;">

            <button onclick="navigateTo('profile');">profile page</button>

            <button onclick="navigateTo('absenceForm');">afwezig melden page</button>

            <button onclick="navigateTo('settings');">settings</button>

            <button onclick="navigateTo('home');">home</button>

        </div>

  

        <div id="page-absenceForm" style="display: none;">

            <button onclick="navigateTo('profile');">profile page</button>

            <button onclick="navigateTo('absenceForm');">afwezig melden page</button>

            <button onclick="navigateTo('settings');">settings</button>

            <button onclick="navigateTo('home');">home</button>

            <h2>Absence Reporting</h2>

            <p id="submit-succes" style="color: blue; display: none;">Sucesfully sent request</p>

            <form id="absence-form">

                <label for="reason">Reason:</label>

                <input type="text" id="reason" name="reason" required><br><br>

                <label for="start-date">Start Date:</label>

                <input type="date" id="start-date" name="start-date" required>

                <input type="time" id="start-time" name="start-time" required><br><br>

                <label for="end-date">End Date:</label>

                <input type="date" id="end-date" name="end-date" required>

                <input type="time" id="end-time" name="end-time" required><br><br>

                <input type="button" id="submit-button" onclick="submitAbsenceForm()" value="Submit">

            </form>

        </div>

  

        <script>

            document.addEventListener("deviceready", onDeviceReady, false);

  

var CheckedIn = false;

  

function submitLoginForm() {

    var username = document.getElementById('username').value;

    var password = document.getElementById('password').value;

    var remember = document.getElementById('Remember').checked;

  

    var xhr = new XMLHttpRequest();

    xhr.open('POST', 'http://localhost/Bliep!/LoginAPI.php', true);

    xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');

  

    xhr.onreadystatechange = function () {

        if (xhr.readyState == 4) {

            if (xhr.status == 200) {

                var response = JSON.parse(xhr.responseText);

  

                if (response.success) {

                    var serialnumb = response.serialNumber;

                    var student_id = response.Student_Id;

                    localStorage.setItem('loggedInUser', JSON.stringify({ username: username, student_id: student_id }));

                    localStorage.setItem('UserSerialNumber', JSON.stringify({ serialNumber: serialnumb.toString() }));

                    navigateTo('home');

                } else {

                    document.getElementById('Login-Fault').style.display = 'block';

                }

            } else {

                document.getElementById('Login-Error').style.display = 'block';

            }

        }

    };

  

    xhr.onerror = function () {

        console.error('Error occurred during login request');

    };

  

    xhr.send('username=' + encodeURIComponent(username) + '&password=' + encodeURIComponent(password));

}

  

function submitAbsenceForm() {

    var student = checkLoginStatus();

    var reason = document.getElementById('reason').value;

    var startDate = document.getElementById('start-date').value;

    var startTime = document.getElementById('start-time').value;

    var endDate = document.getElementById('end-date').value;

    var endTime = document.getElementById('end-time').value;

  

    var formData = new FormData();

    formData.append('student_id', student.student_id)

    formData.append('reason', reason);

    formData.append('start-date', startDate);

    formData.append('start-time', startTime);

    formData.append('end-date', endDate);

    formData.append('end-time', endTime);

  

    var xhr = new XMLHttpRequest();

    xhr.open('POST', 'http://localhost/Bliep!/AbsenceAPI.php', true);

    xhr.onreadystatechange = function () {

        if (xhr.readyState == 4) {

            if (xhr.status == 200) {

                var response = JSON.parse(xhr.responseText);

                console.log(response)

                if (response.succes) {

                    document.getElementById('submit-succes').style.display = 'block';

                }

            } else {

                // Handle errors

            }

        }

    };

  

    xhr.onerror = function () {

        // Handle errors

    };

  

    xhr.send(formData);

}

  

function navigateTo(pageId) {

    document.getElementById('page-home').style.display = 'none';

    document.getElementById('page-login').style.display = 'none';

    document.getElementById('page-profile').style.display = 'none';

    document.getElementById('page-settings').style.display = 'none';

    document.getElementById('page-absenceForm').style.display = 'none';

  

    document.getElementById('page-' + pageId).style.display = 'block';

  

    if (pageId === 'home') {

        var loggedInUser = checkLoginStatus();

        var serialNumb = checkSerialNumberStatus();

        if (loggedInUser) {

            document.getElementById('username-display').innerText = loggedInUser.username;

            animateProgressCircle(29, 331, 500)

        }

        if (serialNumb) {

            document.getElementById('serial-display').innerText = serialNumb;

            checkTimeStatus(function(isCheckedIn, timeStatus) {

                if (isCheckedIn) {

                    document.getElementById('attendance-display').innerText = timeStatus;

                    document.getElementById('CheckInStatus').innerText = "Je bent aanwezig!";

                    CheckedIn = true;

                } else {

                    document.getElementById('attendance-display').innerText = timeStatus;

                    document.getElementById('CheckInStatus').innerText = "Je bent momenteel niet aanwezig.";

                    CheckedIn = false;

                }

            });

        }

    }

}

  

function checkLoginStatus() {

    var userName = localStorage.getItem('loggedInUser');

  

    if (userName) {

        return JSON.parse(userName);

    } else {

        return null;

    }

}

  

function checkSerialNumberStatus() {

    var serialNumberObject = localStorage.getItem('UserSerialNumber');

  

    if (serialNumberObject) {

        var serialNumber = JSON.parse(serialNumberObject).serialNumber;

        return serialNumber;

    } else {

        return null;

    }

}

  

function checkTimeStatus(callback) {

    var serialNumber = checkSerialNumberStatus();

    var exactinfo = false;

  

    var xhr = new XMLHttpRequest();

    xhr.open('POST', 'http://localhost/Bliep!/AttendenceTimeAPI.php', true);

    xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');

  

    xhr.onreadystatechange = function () {

        if (xhr.readyState == 4) {

            if (xhr.status == 200) {

                var response = JSON.parse(xhr.responseText);

  

                if (response.success === true) {

                    callback(response.isCheckedIn, response.total_time_spent);

                    console.log(response)

                } else {

                    document.getElementById('Info-Fault').style.display = 'block';

                }

            } else {

                document.getElementById('Info-Error').style.display = 'block';

            }

        }

    };

  

    xhr.onerror = function () {

        console.error('Error occurred during login request');

    };

  

    xhr.send('SerialNumber=' + encodeURIComponent(serialNumber) + '&ExactInfo=' + encodeURIComponent(exactinfo));

}

  

function logoutUser() {

    localStorage.removeItem('loggedInUser');

    localStorage.removeItem('UserSerialNumber');

    navigateTo('login');

}

  

window.onload = function () {

    animateProgressCircle(29, 331, 500)

    var rememberCheckbox = document.getElementById('Remember');

    var loggedInUser = checkLoginStatus();

    if (loggedInUser) {

        navigateTo('home');

        animateProgressCircle(29, 331, 500)

        if (!rememberCheckbox.checked) {

            navigateTo('login');

            localStorage.removeItem('loggedInUser');

            localStorage.removeItem('UserSerialNumber');

        }

    }

};

  

function DevLogin() {

    localStorage.setItem('loggedInUser', JSON.stringify({ username: '[DEVELOPER]' }));

    localStorage.setItem('UserSerialNumber', JSON.stringify({ serialNumber: '[TEST SERIAL NUMBER]' }))

    document.getElementById('Info-Error').style.display = 'block';

    navigateTo('home');

}

function alertDismissed() {

    // do something

}

  

function Buzztest() {

    navigator.notification.beep(2);

}

  

function AlertTest() {

    navigator.notification.alert(

        'You are the winner!',

        alertDismissed,

        'Game Over',

        'Done'

    );

}

  

function onDeviceReady() {

    console.log(navigator.notification);

    console.log('Device is ready');

    const messaging = firebase.messaging();

    messaging.requestPermission()

        .then(() => {

            console.log('Notification permission granted.');

            return messaging.getToken();

        })

        .then((token) => {

            console.log('FCM token:', token);

        })

        .catch((error) => {

            console.log('Error getting permission or token:', error);

        });

  

    messaging.onMessage((payload) => {

        console.log('Message received:', payload);

    });

}

  

if (!CheckedIn) {

    var message = {

        notification: {

            title: 'Je bent telaat!',

            body: 'De les begint om 09:00 en je bent niet aanwezig!!'

        },

    };

  

    firebase.messaging().send(message)

        .then(function(response) {

            console.log('Message sent successfully:', response);

        })

        .catch(function(error) {

            console.error('Error sending message:', error);

        });

} else {

    console.log('Condition not met, message not sent.');

}

  

function animateProgressCircle(startAngle, endAngle, duration) {

    const progressCircle = document.querySelector('.progresscircle');

    const startTime = performance.now();

    const endTime = startTime + duration;

  

    function animate(currentTime) {

        const elapsedTime = currentTime - startTime;

        const progress = elapsedTime / duration;

        let angle = startAngle + (endAngle - startAngle) * progress;

  

        angle = Math.min(angle, endAngle);

  

        const gradient = `conic-gradient(pink 0deg, lightblue 0 ${angle}deg, orange 0deg)`;

  

        progressCircle.style.backgroundImage = gradient;

  

        if (angle <= endAngle && currentTime < endTime) {

            requestAnimationFrame(animate);

        }

    }

  

    requestAnimationFrame(animate);

}

        </script>

    </body>

    </html>
```