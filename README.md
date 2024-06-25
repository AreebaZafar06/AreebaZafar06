//HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Counter App</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <nav class="navbar">
        <div class="navbar-container">
            <div>
                <a href="#" class="navbar-brand"><b>Counter App</b></a>
                <h3 style="margin: 5; padding: 5; font-size: 1em;"><b>Count your numbers</b></h3>
            </div>
            <ul class="navbar-menu"></ul>
        </div>
    </nav>
    <div class="container">
        <h1>Start Counting</h1>
        <div class="counter">
            <button id="decrement" class="button">-</button>
            <span id="count">0</span>
            <button id="increment" class="button">+</button>
        </div>
        <button id="reset" class="button reset">Reset</button>
    </div>
    <script src="app.js"></script>
</body>
</html>


//CSS
body {
    font-family: Arial, sans-serif;
    margin: 0;
    background-color: #f0f0f0;
}

.navbar {
    background-color: #aaff00;
    padding: 10px 0;
    color: black(255, 255, 255);
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.navbar-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 90%;
    margin: 0 auto;
}

.navbar-brand {
    font-size: 1.5em;
    font-weight: bold;
    text-decoration: none;
    color: black;
}

.navbar-menu {
    list-style: none;
    display: flex;
    gap: 20px;
    margin: 0;
    padding: 0;
}

.navbar-menu li {
    display: inline;
}

.navbar-menu a {
    text-decoration: none;
    color: rgb(255, 255, 255);
    font-size: 1em;
    transition: color 0.3s;
}

.navbar-menu a:hover {
    color: #cce7ff;
}

.container {
    text-align: center;
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
    margin: 100px auto 0; /* Added margin-top to create space below the navbar */
}

h1 {
    margin-bottom: 20px;
    font-size: 2em;
    color: #333333;
}

.counter {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 20px;
}

.button {
    background-color: #0400ff;
    color: white;
    border: none;
    padding: 10px 20px;
    margin: 5px;
    font-size: 1.2em;
    cursor: pointer;
    border-radius: 5px;
    transition: background-color 0.3s;
}

.button:hover {
    background-color: #0400ffe8;
}

#count {
    font-size: 2em;
    margin: 0 20px;
}

.reset {
    background-color: #dc3545;
}

.reset:hover {
    background-color: #c82333;
}

//JavaScript
document.addEventListener('DOMContentLoaded', (event) => {
    let count = 0;

    const countSpan = document.getElementById('count');
    const incrementButton = document.getElementById('increment');
    const decrementButton = document.getElementById('decrement');
    const resetButton = document.getElementById('reset');

    incrementButton.addEventListener('click', () => {
        count++;
        updateCount();
    });

    decrementButton.addEventListener('click', () => {
        count--;
        updateCount();
    });

    resetButton.addEventListener('click', () => {
        count = 0;
        updateCount();
    });

    function updateCount() {
        countSpan.textContent = count;
    }
});
