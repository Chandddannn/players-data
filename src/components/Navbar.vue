<template>
    <nav class="navbar">
      <div class="navbar-container">
        <a class="navbar-brand" href="#">Sportz Interactive</a>
        
        <form class="navbar-search">
          <input class="form-control" type="search" placeholder="Search" aria-label="Search">
          <button class="btn btn-outline-light" type="submit">Search</button>
        </form>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'NavBar'
  }
  </script>
  
  <style scoped>
  .navbar {
    background-color: #1e1e1e;
    padding: 15px;
    width: 100%;
    position: sticky;
    top: 0;
    z-index: 1000;
    overflow-x: hidden;
    box-sizing: border-box;
    border-bottom: 2px solid green; 
    /* Ensure padding is included in element's width */
  }
  
  .navbar-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%; /* Full width of the navbar */
    max-width: 100vw; /* Prevent overflow beyond the viewport width */
    padding: 0 10px; /* Adjust padding to avoid overflow */
    box-sizing: border-box;
    flex-wrap: wrap; /* Allow elements to wrap if necessary */
  }
  
  .navbar-brand {
    font-size: 24px;
    font-weight: bold;
    color: #fff;
    text-decoration: none;
    white-space: nowrap; /* Prevent text wrapping */
  }
  
  .navbar-links {
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
  }
  
  .nav-item {
    display: inline-block;
  }
  
  .nav-link {
    color: #fff;
    text-decoration: none;
    font-size: 18px;
  }
  
  .nav-link:hover {
    color: #00ff00;
  }
  
  .navbar-search {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
  }
  
  .form-control {
    background-color: #333;
    border: 1px solid #555;
    color: #fff;
    padding: 10px;
    margin-right: 10px;
  }
  
  .form-control::placeholder {
    color: #999;
  }
  
  .btn-outline-light {
    border: 1px solid #999;
    color:black;
    padding: 10px 20px;
    border-radius: 8px;
    cursor: pointer;
    border-color: #00ff00;
  }
  
  .btn-outline-light:hover {
    background-color: #00ff00;
    color: #000;
  }
  
  /* Media Query for smaller screens */
  @media (max-width: 768px) {
    .navbar-container {
      flex-direction: column; /* Stack elements vertically */
      align-items: center; /* Center align the elements */
    }
  
    .navbar-links {
      flex-direction: column; /* Stack links vertically */
      gap: 10px;
      margin-top: 10px;
    }
  
    .navbar-search {
      margin-top: 10px;
      width: 100%; /* Full width for mobile */
      justify-content: center;
    }
  
    .form-control {
      width: 100%;
      margin: 10px 0;
    }
  
    .navbar-brand {
      font-size: 20px; /* Slightly smaller font for mobile */
    }
  
    .nav-link {
      font-size: 16px; /* Smaller font size for mobile */
    }
  }
  
  /* Media Query for very small screens (e.g., phones) */
  @media (max-width: 480px) {
    .navbar-brand {
      font-size: 18px;
    }
  
    .nav-link {
      font-size: 14px;
    }
  
    .form-control {
      font-size: 14px;
    }
  
    .btn-outline-light {
      padding: 5px 8px;
      font-size: 14px;
    }
  }
  </style>
  