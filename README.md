
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Colorful Login Page</title>
  <style>
    /* Reset default browser styles */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff6ec7, #7873f5, #42e695);
      background-size: 300% 300%;
      animation: gradientShift 6s ease infinite;
    }

    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .login-box {
      background: rgba(255, 255, 255, 0.15);
      backdrop-filter: blur(15px);
      border-radius: 15px;
      padding: 40px;
      width: 350px;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
      text-align: center;
      color: #fff;
    }

    .login-box h2 {
      margin-bottom: 20px;
      font-size: 2em;
      letter-spacing: 1px;
    }

    .input-box {
      position: relative;
      margin: 25px 0;
    }

    .input-box input {
      width: 100%;
      padding: 12px 15px;
      border: none;
      border-radius: 8px;
      outline: none;
      background: rgba(255, 255, 255, 0.2);
      color: #fff;
      font-size: 1em;
      transition: background 0.3s;
    }

    .input-box input::placeholder {
      color: #eee;
    }

    .input-box input:focus {
      background: rgba(255, 255, 255, 0.3);
    }

    .btn {
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 8px;
      font-size: 1.1em;
      font-weight: bold;
      color: #fff;
      cursor: pointer;
      background: linear-gradient(90deg, #ff8a00, #e52e71);
      transition: 0.3s;
    }

    .btn:hover {
      transform: translateY(-2px);
      background: linear-gradient(90deg, #e52e71, #ff8a00);
    }

    .signup-link {
      margin-top: 20px;
      font-size: 0.9em;
    }

    .signup-link a {
      color: #fff;
      font-weight: bold;
      text-decoration: none;
    }

    .signup-link a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>

  <div class="login-box">
    <h2>Welcome Back!</h2>
    <form>
      <div class="input-box">
        <input type="text" placeholder="Username" required />
      </div>
      <div class="input-box">
        <input type="password" placeholder="Password" required />
      </div>
      <button type="submit" class="btn">Login</button>
      <div class="signup-link">
        Don’t have an account? <a href="#">Sign Up</a>
      </div>
    </form>
  </div>

</body>
</html>
