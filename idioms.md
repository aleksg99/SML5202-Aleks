<html>
<head>
<title>Page Title</title>
</head>
<body>

<h1> Random Idiom Using JSON </h1>

<button type="button" class="new-quote button">Show Idiom</button>

<dl id="quote"></dl>

<script>
const endpoint = 'https://aleksg99.github.io/SML5202-Aleks/datasets/idioms.json';

function getQuote() {
fetch(endpoint)
.then(function (response) {
return response.json();
})

.then(function(data){
let id = Math.floor(Math.random() * 5);
let idiom = (data.idioms[id].idiom);
let meaning = (data.idioms[id].meaning);
let example =(data.idioms[id].example);


document.querySelector("#quote").innerHTML = "<dt>" + idiom + "<dt>" + "<dd><strong>Example:<strong> " + example + "</dd><dd><strong>Meaning:</strong> " + meaning + "</dd> " ;

//console.log(data.idioms[id].idiom)
})

.catch(function () {
console.log("Error occurred");
});
}

const newQuoteButton = document.querySelector('.new-quote');
newQuoteButton.addEventListener('click', getQuote);

</script>
</body>
</html>
