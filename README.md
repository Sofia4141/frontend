<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Card Manager</title>
<style>
    body {
        font-family: Arial, sans-serif;
    }

    .container {
        max-width: 800px;
        margin: 0 auto;
        padding: 20px;
    }

    .card {
        border: 1px solid #ccc;
        border-radius: 5px;
        padding: 20px;
        margin-bottom: 20px;
    }

    .btn {
        display: inline-block;
        padding: 10px 20px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }

    .btn.add {
        background-color: #28a745;
    }

    .btn.remove {
        background-color: #dc3545;
    }
</style>
</head>
<body>
<div class="container">
    <div class="card" id="card1">
        <h3>Card 1</h3>
        <p>This is card 1 content.</p>
    </div>
    <div class="card" id="card2">
        <h3>Card 2</h3>
        <p>This is card 2 content.</p>
    </div>
    <div class="card" id="card3">
        <h3>Card 3</h3>
        <p>This is card 3 content.</p>
    </div>
    <div class="card" id="card4">
        <h3>Card 4</h3>
        <p>This is card 4 content.</p>
    </div>
    <button class="btn add" onclick="addCard()">Add Card</button>
    <button class="btn remove" onclick="removeCard()">Remove Card</button>
</div>

<script>
    function addCard() {
        const container = document.querySelector('.container');
        const newCard = document.createElement('div');
        newCard.className = 'card';
        newCard.innerHTML = `
            <h3>Card ${container.children.length - 1}</h3>
            <p>This is card ${container.children.length - 1} content.</p>
        `;
        container.insertBefore(newCard, container.lastElementChild);
    }

    function removeCard() {
        const container = document.querySelector('.container');
        if (container.children.length > 4) {
            container.removeChild(container.lastElementChild);
        } else {
            alert("Can't remove the last card!");
        }
    }
</script>
</body>
</html>
