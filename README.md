<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
  <link rel="stylesheet" href="styles.css">
  <title>Your E-commerce Website</title>
</head>
<body>
<style>
    button {
    display: block;
    margin-top: 5px;
    padding: 7px;
    width: 150px;
    background-color: blue;
    color: #fff;
    border: none;
    cursor: pointer;
}
* {
      box-sizing: border-box;   
        margin: 0;
            padding: 0;
        }
        select {
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 5px;
            outline: none;
            transition: border-color 0.3s;
        }

        select:hover,
        select:focus {
            border-color: #007bff;
        }
</style>
  <!-- Navbar -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand" href="#">Igtradingmaster</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav ml-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home</a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">Customer Support</a>
          </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Terms And Condition</a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">Fraud Or Scam</a>
          </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Contact To Admin</a>
        </li>
      </ul>
    </div>
  </nav>

  <!-- Hero Section -->
  <div class="hero-section">
    <div class="container">
      <center><h1>Welcome to Your Igtradingmaster Store</h1>
      <center><p>Discover amazing products and shop with ease.</p>
      <center><a href="#" class="btn btn-primary">Shop Now</a>
    </div>
  </div>

  <!-- Product Section -->
  <div class="container mt-5">
    <div class="row">
      <!-- Product 1 -->
      <div class="col-md-4">
        <div class="card">
          <img src="C:\Users\vedbh\Downloads\1609685339554.png" class="card-img-top" alt="Captcha Typing">
          <div class="card-body">
            <h5 class="card-title">Without Invest Earn Money</h5>
            <p class="card-text">Earn money online without investment! Explore freelance opportunities, such as writing, graphic design, or programming on platforms like Upwork and Fiverr. Participate in online surveys, review websites, or monetize your skills through content creation on platforms like YouTube or Medium. Discover numerous ways to generate income without spending a time!</p>
            <label for="cars">Choose a Curruncy:</label>

            <select id="cars" name="cars" required>
                <option value="volvo">INR 19.99 Ruppes</option>
                <option value="saab">USD 0.24053</option>
                <option value="mercedes">EUROS 0.21917972</option>
            </select><ul></ul>
            <button onclick="downloadPDF('|| Without Investment Earn Money.pdf ||')">CLICK TO PAY</button>
          </div>
        </div>
      </div>

      <!-- Product 2 -->
      <div class="col-md-4">
        <div class="card">
          <img src="C:\Users\vedbh\Downloads\2.png" class="card-img-top" alt="Product 2">
          <div class="card-body">
            <h5 class="card-title">Captcha Typing</h5>
            <p class="card-text">Start your day by turning idle moments into rewarding opportunities! Engage in captcha typing and earn effortlessly each morning. Unlock financial possibilities with a simple yet lucrative task. Embrace the convenience of online earnings, making your mornings both productive and profitable. Join now for a seamless journey towards financial independence!"</p>
            <select id="cars" name="cars" required>
                <option value="volvo">INR 19.99 Ruppes</option>
                <option value="saab">USD 0.24053</option>
                <option value="mercedes">EUROS 0.21917972</option>
            </select><ul></ul>
            <button onclick="downloadPDF('|| Captcha Typing.pdf ||')">CLICK TO PAY</button>
          </div>
        </div>
      </div>
 <!-- Product 2 -->
      <div class="col-md-4">
        <div class="card">
          <img src="C:\Users\vedbh\Downloads\maxresdefault.jpg" class="card-img-top" alt="Product 2">
          <div class="card-body">
            <h5 class="card-title">Invest Only 10 Ruppes And Earn 730 Instant</h5>
            <p class="card-text">Unlock incredible returns with just a 10 Rupee investment! Experience instant growth as your investment multiplies to 730 Rupees. Don't miss this golden opportunity to make your money work for you. Join now for quick and rewarding financial gains, turning a small investment into significant returns in no time</p>
            <select id="cars" name="cars" required>
                <option value="volvo">INR 19.99 Ruppes</option>
                <option value="saab">USD 0.24053</option>
                <option value="mercedes">EUROS 0.21917972</option>
            </select><ul></ul>
            <button onclick="downloadPDF('|| Invest Only 10 Ruppes And Earn 730 Instant.pdf ||')">CLICK TO PAY</button>
          </div>
        </div>
      </div>
       <!-- Product 2 -->
      <div class="col-md-4">
        <div class="card">
          <img src="C:\Users\vedbh\Downloads\4.jpg" class="card-img-top" alt="Product 2">
          <div class="card-body">
            <h5 class="card-title">Quiz or Show Ads And Correct Ans Get 100,500,1000 Instant Your UPI</h5>
            <p class="card-text">Engage, Learn, and Win! Participate in our Quiz or Show Ads challenge for a chance to win instant rewards of 100, 500, or 1000! Simply answer correctly and claim your prize directly to your UPI. Exciting, interactive, and rewarding – your knowledge pays off instantly. Join the fun now!</p>
            <select id="cars" name="cars" required>
                <option value="volvo">INR 19.99 Ruppes</option>
                <option value="saab">USD 0.24053</option>
                <option value="mercedes">EUROS 0.21917972</option>
            </select><ul></ul>
            <button onclick="downloadPDF('|| Quiz or Show Ads And Correct Ans Get 100,500,1000 Instant Your UPI.pdf ||')">CLICK TO PAY</button>
          </div>
        </div>
      </div>
      <!-- Product 3 -->
      <div class="col-md-4">
        <div class="card">
          <img src="C:\Users\vedbh\Downloads\5.jpg" class="card-img-top" alt="Product 3">
          <div class="card-body">
            <h5 class="card-title">Watch Video And Earn Money Instant Withdraw In Your UPI</h5>
            <p class="card-text">Unlock a world of instant earnings! Watch engaging videos and earn real money with immediate UPI withdrawals. Experience a seamless way to boost your income effortlessly. Don't miss out on this incredible opportunity! Join now and start earning instantly. Fast, reliable, and hassle-free - your financial freedom awaits!</p>
            <select id="cars" name="cars" required>
                <option value="volvo">INR 19.99 Ruppes</option>
                <option value="saab">USD 0.24053</option>
                <option value="mercedes">EUROS 0.21917972</option>
            </select><ul></ul>
            <button onclick="downloadPDF('|| Watch Video And Earn Money Instant Withdraw In Your UPI.pdf ||')">CLICK TO PAY</button>
          </div>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card">
          <img src="C:\Users\vedbh\Downloads\6.jpg" class="card-img-top" alt="Product 3">
          <div class="card-body">
            <h5 class="card-title">Signup Bonus 500 Rupees,900 Ruppes InvestmentThen You Get 2500 Ruppes, instant Withdraw Your UPI</h5>
            <p class="card-text">Unlock financial gains with a lucrative offer! Sign up today for a generous 500 Rupees bonus. Invest just 900 Rupees and watch your returns soar to 2500 Rupees! Enjoy instant withdrawals to your UPI. Seize this opportunity for quick and easy profits. Don't miss out on financial success!</p>
            <select id="cars" name="cars" required>
                <option value="volvo">INR 19.99 Ruppes</option>
                <option value="saab">USD 0.24053</option>
                <option value="mercedes">EUROS 0.21917972</option>
            </select><ul></ul>
            <button onclick="downloadPDF('|| Signup Bonus 500 Rupees,900 Ruppes InvestmentThen You Get 2500 Ruppes, instant Withdraw Your UPI.pdf ||')">CLICK TO PAY</button>
          </div>
        </div>
      </div>

    </div>
  </div>
  
  <!-- Footer -->
  <footer class="bg-dark text-white text-center py-3">
    <p>&copy; 2024 Igtradingmaster</p>
  </footer>

  <!-- Scripts -->
  <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.1/dist/umd/popper.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
  <!-- Bootstrap JS and jQuery -->
  <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
  <script>
    function downloadPDF(pdfName) {
    // Simulate download (replace this with actual download logic)
    alert(`First Payment And Get Your Course ${pdfName}`);
    
    // Redirect to the second page (replace 'second_page.html' with the actual page)
    window.location.href = 'payment.html';
}
</script>
