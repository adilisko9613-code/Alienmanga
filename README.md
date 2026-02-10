<!DOCTYPE html>
<html>
<head>
  <title>AlienManga Giriş</title>
  <script type="module">
    // Firebase SDK import
    import { initializeApp } from "https://www.gstatic.com/firebasejs/10.1.0/firebase-app.js";
    import { getAuth, signInWithPopup, GoogleAuthProvider } from "https://www.gstatic.com/firebasejs/10.1.0/firebase-auth.js";

    // Firebase config (senin gönderdiğin)
    const firebaseConfig = {
      apiKey: "AIzaSyCrblq-TbJ5n-MWP0O7Fro-IMFIpK0DiHU",
      authDomain: "alienmanga.firebaseapp.com",
      projectId: "alienmanga",
      storageBucket: "alienmanga.firebasestorage.app",
      messagingSenderId: "934128530929",
      appId: "1:934128530929:web:84dbeedc60bbde44374050",
      measurementId: "G-GMK3J3ZRER"
    };

    // Firebase başlat
    const app = initializeApp(firebaseConfig);
    const auth = getAuth(app);
    const provider = new GoogleAuthProvider();

    // Google ile giriş fonksiyonu
    window.googleLogin = function() {
      signInWithPopup(auth, provider)
        .then((result) => {
          const user = result.user;
          alert("Giriş başarılı: " + user.displayName + " (" + user.email + ")");
        })
        .catch((error) => alert("Hata: " + error.message));
    }
  </script>
</head>
<body>
  <h1>AlienManga - Google ile Giriş</h1>
  <button onclick="googleLogin()">Google ile Giriş Yap</button>
</body>
</html>
