<!DOCTYPE html>
<html>
<head>
  <title>Login / Signup</title>
</head>
<body>
  <h2>Sign Up</h2>
  <input id="signup-email" type="email" placeholder="Email" />
  <input id="signup-password" type="password" placeholder="Password" />
  <button onclick="signUp()">Sign Up</button>

  <h2>Login</h2>
  <input id="login-email" type="email" placeholder="Email" />
  <input id="login-password" type="password" placeholder="Password" />
  <button onclick="logIn()">Login</button>

  <p id="message"></p>

  <!-- Firebase JS SDK -->
  <script src="https://www.gstatic.com/firebasejs/10.4.0/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.4.0/firebase-auth-compat.js"></script>

  <script>
    // Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSyAWbY94YIYW-mwOdQaDJ9_DE3cqwGTM-4g",
  authDomain: "login-for-the-edtech.firebaseapp.com",
  projectId: "login-for-the-edtech",
  storageBucket: "login-for-the-edtech.firebasestorage.app",
  messagingSenderId: "251701827822",
  appId: "1:251701827822:web:6edcf8f99c63d6fe143bff"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);

    firebase.initializeApp(firebaseConfig);
    const auth = firebase.auth();

    function signUp() {
      const email = document.getElementById('signup-email').value;
      const password = document.getElementById('signup-password').value;
      auth.createUserWithEmailAndPassword(email, password)
        .then(() => {
          document.getElementById('message').innerText = 'Signup successful!';
        })
        .catch(error => {
          document.getElementById('message').innerText = error.message;
        });
    }

    function logIn() {
      const email = document.getElementById('login-email').value;
      const password = document.getElementById('login-password').value;
      auth.signInWithEmailAndPassword(email, password)
        .then(() => {
          document.getElementById('message').innerText = 'Login successful!';
        })
        .catch(error => {
          document.getElementById('message').innerText = error.message;
        });
    }
  </script>
</body>
</html>

