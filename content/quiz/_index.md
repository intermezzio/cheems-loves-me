---
title: "Quiz"
date: 2023-01-04T00:24:33-05:00
draft: false
---

<form onsubmit="getAnswers(event)">
<label for="question1">Do you prefer to spend time alone or with others?</label><br>
<input type="radio" name="question1" value="alone">Alone<br>
<input type="radio" name="question1" value="with others">With others<br>
<br>
<label for="question2">Do you consider yourself more of a risk-taker or a cautious person?</label><br>
<input type="radio" name="question2" value="risk-taker">Risk-taker<br>
<input type="radio" name="question2" value="cautious">Cautious<br>
<br>
<label for="question3">Do you prefer a structured or a flexible schedule?</label><br>
<input type="radio" name="question3" value="structured">Structured<br>
<input type="radio" name="question3" value="flexible">Flexible<br>
<br>
<input type="submit" value="Submit">
</form> 

<div id="results">

<script type="text/javascript">
function getAnswers(event) {
  event.preventDefault();
  var answers = [];
  var question1 = document.querySelector('input[name="question1"]:checked').value;
  answers.push(question1);
  var question2 = document.querySelector('input[name="question2"]:checked').value;
  answers.push(question2);
  var question3 = document.querySelector('input[name="question3"]:checked').value;
  answers.push(question3);
  
  var resultsDiv = document.getElementById('results');

  resultsDiv.innerHTML = answers
}
</script>