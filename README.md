<!DOCTYPE html>
<html>
<head>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background: url('https://i.pinimg.com/736x/f9/6f/f2/f96ff2dd5e11fdeb8023a5bbf04e5591.jpg') no-repeat center center fixed;
            background-size: cover;
        }
        .container {
            text-align: center;
            max-width: 600px;
            margin: auto;
            background-color: rgba(255, 255, 255, 0.2); /* Add a white background with transparency */
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
        }
        textarea {
            width: 100%;
        }
        input[type="text"] {
            width: calc(100% - 12px);
        }
        button {
            margin: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <p>Edit the sentence below:</p>
        <textarea id="textArea" name="text" rows="10" cols="30">The quick brown fox jumps over the lazy dog.</textarea><br>

        <label>Find what: </label>
        <input type="text" id="findWhat" placeholder="Enter the word"><br>

        <label>Replace with: </label>
        <input type="text" id="replaceWith" placeholder="Replace the word with">
        <button type="button" onclick="replaceWord();">Replace</button>
        <button type="button" onclick="clearNow();">Clear</button>
        
        <h2></h2>
        <label>Length of the sentence:</label>
        <p id="demo"></p>
        
        <label>Uppercase:</label>
        <p id="demo4"></p>
        <label>Lowercase:</label>
        <p id="demo5"></p>
        <label>Enter Word: </label>
        <input type="text" id="enterWord" placeholder="Enter the word"><br>
        <label>Does the word include in the sentence?:</label>
        <p id="demo2"></p>
        <label>Search:</label>
        <p id="demo3"></p>

        <button type="button" onclick="formatText();">Answer</button>
        <button type="button" onclick="resetNow();">Clear</button>
        <button type="button" onclick="changeBackgroundNewYear();">New Year Background</button>
        <button type="button" onclick="changeBackgroundChristmas();">Christmas Background</button>
        <button type="button" onclick="changedBackgroundHalloween();">Halloween Background</button>
        <button type="button" onclick="backgroundReset();">Reset Background</button>
    </div>

    <script>
        function replaceWord() {
            let textArea = document.getElementById("textArea").value;
            let findWhat = document.getElementById("findWhat").value;
            let replaceWith = document.getElementById("replaceWith").value;
            let newText = textArea.replace(findWhat, replaceWith);
            document.getElementById("textArea").value = newText;
        }

        function clearNow() {
            document.getElementById("findWhat").value = "";
            document.getElementById("replaceWith").value = "";
            console.log('clear');
        }

        function formatText() {
            let text = document.getElementById("textArea").value;
            let searchWord = document.getElementById("enterWord").value;

            let length = text.length;
            let includesWord = text.includes(searchWord);
            let position = text.search(searchWord);
            let resultUppercase = text.toUpperCase();
            let resultLowercase = text.toLowerCase();

            document.getElementById("demo").innerHTML = length;
            document.getElementById("demo2").innerHTML = includesWord ? "Yes" : "No";
            document.getElementById("demo3").innerHTML = position !== -1 ? position : "Not found";
            document.getElementById("demo4").innerHTML = resultUppercase;
            document.getElementById("demo5").innerHTML = resultLowercase;
        }

        function resetNow() {
            document.getElementById("enterWord").value = "";
            console.log('clear');
        }

        function changeBackgroundNewYear() {
            document.body.style.backgroundImage = "url('https://i.pinimg.com/736x/79/72/1d/79721de472349bc7fa61a8d911cc041e.jpg')";
        }
        function changeBackgroundChristmas() {
            document.body.style.backgroundImage = "url('https://i.pinimg.com/736x/14/8f/45/148f45a7f94b5e191f1b56c1d7f577a3.jpg')";
        }
        function changedBackgroundHalloween() {
            document.body.style.backgroundImage = "url('https://i.pinimg.com/736x/69/19/79/691979674b9dd857f19aac50de41ff62.jpg')";
        }
        function backgroundReset() {
            document.body.style.backgroundImage = "url('https://i.pinimg.com/736x/f9/6f/f2/f96ff2dd5e11fdeb8023a5bbf04e5591.jpg')";
        }
    </script>
</body>
</html>
