<!DOCTYPE html>
<html>
<head>
    <title>Test Table</title>
    <style>
        #btetoiled, #btetoileo, #btetoiler, #btetoileve, #btetoileb, #btetoilevi {
            width: 40vh;
            height: 10vh;
            position: absolute;
            border-radius: 20%;
            visibility: visible;
        }
        #btetoiled { top: 24%; left: 20%; background-color: gold; border: 2px solid orange; }
        #btetoileo { top: 24%; left: 60%; background-color: orange; border: 2px solid brown; }
        #btetoiler { top: 44%; left: 20%; background-color: red; border: 2px solid black; }
        #btetoileve { top: 44%; left: 60%; background-color: lime; border: 2px solid green; }
        #btetoileb { top: 64%; left: 20%; background-color: turquoise; border: 2px solid blue; }
        #btetoilevi { top: 64%; left: 60%; background-color: fuchsia; border: 2px solid purple; }
        #bravo, #juste, #rate { top: 20%; left: 0%; position: absolute; visibility: hidden; }
        #bravo { color: green; }
        #juste { color: blue; }
        #rate { color: red; }
    </style>
</head>
<body>
    <button id="btetoiled">Étoile dorée (0, 1 et 2)</button>
    <button id="btetoileo">Étoile orange (5 et 10)</button>
    <button id="btetoiler">Étoile rouge (3)</button>
    <button id="btetoileve">Étoile verte (4)</button>
    <button id="btetoileb">Étoile bleu (6 et 7)</button>
    <button id="btetoilevi">Étoile violette (8 et 9)</button>
    
    <p id="bravo"><strong>! BRAVO !</strong></p>
    <p id="juste"><strong>Pas mal !</strong></p>
    <p id="rate"><strong>Va réviser tes tables !</strong></p>
    
    <script>
        document.getElementById("btetoiled").onclick = function() { lanctabl([0, 1, 2], "btetoiled"); };
        document.getElementById("btetoileo").onclick = function() { lanctabl([5, 10], "btetoileo"); };
        document.getElementById("btetoiler").onclick = function() { lanctabl([3], "btetoiler"); };
        document.getElementById("btetoileve").onclick = function() { lanctabl([4], "btetoileve"); };
        document.getElementById("btetoileb").onclick = function() { lanctabl([6, 7], "btetoileb"); };
        document.getElementById("btetoilevi").onclick = function() { lanctabl([8, 9], "btetoilevi"); };
        
        function lanctabl(tables, buttonId) {
            var score = 0;
            for (var i = 0; i < 10; i++) {
                var table = tables[Math.floor(Math.random() * tables.length)];
                var chiffre = Math.floor(Math.random() * 10);
                var reponse = prompt("Combien fait " + table + " × " + chiffre);
                if (parseInt(reponse) === table * chiffre) score++;
            }
            alert("Ton score est : " + score + " / 10");
            hideButtons();
            displayResult(score);
        }
        
        function hideButtons() {
            document.getElementById("btetoiled").style.visibility = "hidden";
            document.getElementById("btetoileo").style.visibility = "hidden";
            document.getElementById("btetoiler").style.visibility = "hidden";
            document.getElementById("btetoileve").style.visibility = "hidden";
            document.getElementById("btetoileb").style.visibility = "hidden";
            document.getElementById("btetoilevi").style.visibility = "hidden";
        }
        
        function displayResult(score) {
            document.getElementById("bravo").style.visibility = score > 8 ? "visible" : "hidden";
            document.getElementById("juste").style.visibility = score === 8 ? "visible" : "hidden";
            document.getElementById("rate").style.visibility = score < 8 ? "visible" : "hidden";
        }
    </script>
</body>
</html>
