# (index.html) 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Fetch API Example</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="container">
    <h1>User Information</h1>
    <button onclick="fetchUsers()">Reload Data</button>
    <div id="user-list"></div>
  </div>

  <script src="script.js"></script>
</body>
</html>

# (styles.css) 
body {
  font-family: Arial, sans-serif;
  background-color: #f9f9f9;
  margin: 0;
  padding: 20px;
}

.container {
  max-width: 800px;
  margin: auto;
}

#user-list {
  margin-top: 20px;
}

.user-card {
  background: #fff;
  padding: 15px;
  margin-bottom: 10px;
  border-radius: 8px;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.1);
}

#  (script.js) 
function fetchUsers() {
  const userList = document.getElementById('user-list');
  userList.innerHTML = 'Loading...';

  fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => {
      if (!response.ok) throw new Error('Network response was not OK');
      return response.json();
    })
    .then(users => {
      userList.innerHTML = '';
      users.forEach(user => {
        const userCard = document.createElement('div');
        userCard.className = 'user-card';
        userCard.innerHTML = `
          <h3>${user.name}</h3>
          <p><strong>Email:</strong> ${user.email}</p>
          <p><strong>Address:</strong> ${user.address.street}, ${user.address.city}</p>
        `;
        userList.appendChild(userCard);
      });
    })
    .catch(error => {
      userList.innerHTML = `<p style="color:red;">Error: ${error.message}</p>`;
    });
}

// Load data initially
window.onload = fetchUsers;
# Features Included 

Data fetch from public API.

Graceful error handling with catch.

Reload button for testing and re-fetching.

Clean, readable layout using CSS.

 # i have done this task by using html. css. scriptjs . 

 # OUTCOME

 ![17494533943396751392873716258387](https://github.com/user-attachments/assets/42554988-e75c-48f3-9c71-117acad3fbde)

