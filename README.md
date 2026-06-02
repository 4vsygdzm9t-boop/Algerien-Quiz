# Algerien-Quiz
<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Algerien Quiz</title>

<style>
body{
    font-family: Arial, sans-serif;
    background:#f4f4f4;
    padding:20px;
}

h1{
    text-align:center;
}

.quiz{
    max-width:900px;
    margin:auto;
}

.question{
    background:white;
    padding:15px;
    margin-bottom:20px;
    border-radius:10px;
    box-shadow:0 0 5px rgba(0,0,0,0.2);
}

.answer{
    display:block;
    border:2px solid #999;
    border-radius:8px;
    padding:10px;
    margin:8px 0;
    cursor:pointer;
}

.correct{
    background:#4CAF50;
    color:white;
    border-color:#4CAF50;
}

.wrong{
    background:#f44336;
    color:white;
    border-color:#f44336;
}

.result{
    font-weight:bold;
    margin-top:10px;
}
</style>
</head>

<body>

<h1>🇩🇿 Algerien Quiz</h1>

<div class="quiz" id="quiz"></div>

<script>

const questions = [
{
question:"1. Welche Farben hat die Nationalflagge von Algerien?",
answers:[
"A) Rot und Gelb",
"B) Grün und Weiß mit einem roten Halbmond und Stern",
"C) Blau, Weiß, Rot"
],
correct:1
},
{
question:"2. Auf welchem Kontinent liegt Algerien?",
answers:[
"A) Asien",
"B) Europa",
"C) Afrika"
],
correct:2
},
{
question:"3. Welche Währung nutzt man in Algerien?",
answers:[
"A) Algerischer Dinar",
"B) Euro",
"C) Algerischer Dirham"
],
correct:0
},
{
question:"4. Welches Meer grenzt im Norden an Algerien?",
answers:[
"A) Rotes Meer",
"B) Mittelmeer",
"C) Schwarzes Meer"
],
correct:1
},
{
question:"5. Was ist das am häufigsten genutzte Transportmittel für Touristen, um tief in die algerische Sahara zu reisen?",
answers:[
"A) U-Bahn",
"B) Geländewagen (4x4)",
"C) Kreuzfahrtschiff"
],
correct:1
},
{
question:"6. Wie heißt der höchste Berg Algeriens, der im Ahaggar-Gebirge liegt?",
answers:[
"A) Tahat",
"B) Toubkal",
"C) Kilimandscharo"
],
correct:0
},
{
question:"7. Welcher berühmte französische Schriftsteller und Nobelpreisträger wurde in Algerien geboren?",
answers:[
"A) Jean-Paul Sartre",
"B) Albert Camus",
"C) Victor Hugo"
],
correct:1
},
{
question:"8. Die Wüstenstadt Ghardaïa liegt in einem berühmten Tal. Wie heißt dieses Tal?",
answers:[
"A) M'Zab-Tal",
"B) Tal der Könige",
"C) Todra-Tal"
],
correct:0
},
{
question:"9. Welches Land ist Algeriens östlicher Nachbar mit der kürzesten gemeinsamen Grenze?",
answers:[
"A) Marokko",
"B) Libyen",
"C) Tunesien"
],
correct:2
},
{
question:"10. In welchem Jahr fand das historische Referendum statt, bei dem die algerische Bevölkerung für die Unabhängigkeit stimmte?",
answers:[
"A) 1954",
"B) 1962",
"C) 1975"
],
correct:1
}
];

const quiz = document.getElementById("quiz");

questions.forEach((q,index)=>{

const div=document.createElement("div");
div.className="question";

div.innerHTML=`<h3>${q.question}</h3>`;

q.answers.forEach((answer,i)=>{

const btn=document.createElement("div");
btn.className="answer";
btn.textContent=answer;

btn.addEventListener("click",()=>{

if(div.dataset.answered) return;

div.dataset.answered=true;

if(i===q.correct){
btn.classList.add("correct");
result.textContent="✅ Richtig!";
result.style.color="green";
}
else{
btn.classList.add("wrong");
result.textContent="❌ Falsch!";
result.style.color="red";
}
});

div.appendChild(btn);

});

const result=document.createElement("div");
result.className="result";
div.appendChild(result);

quiz.appendChild(div);

});

</script>

</body>
</html>