<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GitHub Profile</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

<div class="container">
  <div class="profile-header">
    <img src="https://avatars.githubusercontent.com/ficky230596" alt="Profile Picture">
    <h1>Your Name</h1>
    <p>@yourusername</p>
    <p>Software Developer</p>
  </div>
  
  <div class="profile-stats">
    <div class="stat">
      <span>Repositories</span>
      <span id="repos">Loading...</span>
    </div>
    <div class="stat">
      <span>Followers</span>
      <span id="followers">Loading...</span>
    </div>
    <div class="stat">
      <span>IG</span>
      <span id="following">url : https://www.instagram.com/f_r_23/</span>
    </div>
  </div>
</div>

<script>
  // Fetch data from GitHub API
  fetch('https://api.github.com/users/ficky230596')
    .then(response => response.json())
    .then(data => {
      document.getElementById('repos').textContent = data.public_repos;
      document.getElementById('followers').textContent = data.followers;
      document.getElementById('following').textContent = data.following;
    })
    .catch(error => console.error('Error fetching data:', error));
</script>

</body>
</html>
