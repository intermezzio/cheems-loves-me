---
title: "Quiz"
date: 2023-01-04T00:24:33-05:00
draft: false
---

<form id="cheem-quiz">
  <h3>How much do you like cheems?</h3>
  <label for="q1">1. How often do you think about cheems?</label><br>
  <input type="radio" name="q1" value="a"> Never<br>
  <input type="radio" name="q1" value="b"> Occasionally<br>
  <input type="radio" name="q1" value="c"> Often<br>
  <input type="radio" name="q1" value="d"> Constantly<br><br>
  
  <label for="q2">2. Have you ever owned a cheem?</label><br>
  <input type="radio" name="q2" value="a"> No<br>
  <input type="radio" name="q2" value="b"> Yes, but it didn't work out<br>
  <input type="radio" name="q2" value="c"> Yes, and it was a great experience<br>
  <input type="radio" name="q2" value="d"> Yes, and it is still a beloved member of my family<br><br>
  
  <label for="q3">3. How do you feel when you see a cheem?</label><br>
  <input type="radio" name="q3" value="a"> Indifferent<br>
  <input type="radio" name="q3" value="b"> Happy<br>
  <input type="radio" name="q3" value="c"> Excited<br>
  <input type="radio" name="q3" value="d"> Overwhelmed with love<br><br>
  
  <label for="q4">4. How do you react when someone mentions cheems in conversation?</label><br>
  <input type="radio" name="q4" value="a"> I don't pay attention<br>
  <input type="radio" name="q4" value="b"> I smile and listen<br>
  <input type="radio" name="q4" value="c"> I get excited and start talking about my own experiences with cheems<br>
  <input type="radio" name="q4" value="d"> I can't control my emotions and start crying tears of joy<br><br>
  
  <label for="q5">5. How much do you enjoy seeing pictures or videos of cheems on the internet?</label><br>
  <input type="radio" name="q5" value="a"> Not at all<br>
  <input type="radio" name="q5" value="b"> A little bit<br>
  <input type="radio" name="q5" value="c"> Moderately<br>
  <input type="radio" name="q5" value="d"> Extremely<br><br>

  <label for="q6">6. Have you ever visited a cheem in person?</label><br>
  <input type="radio" name="q6" value="a"> No<br>
  <input type="radio" name="q6" value="b"> Yes, but it was a disappointment<br>
  <input type="radio" name="q6" value="c"> Yes, and it was a pleasant experience<br>
  <input type="radio" name="q6" value="d"> Yes, and it was one of the best experiences of my life<br><br>
  
  <label for="q7">7. Do you have any cheem-related items in your home?</label><br>
  <input type="radio" name="q7" value="a"> No<br>
  <input type="radio" name="q7" value="b"> Yes, a few small items<br>
  <input type="radio" name="q7" value="c"> Yes, a moderate number of items<br>
  <input type="radio" name="q7" value="d"> Yes, my home is filled with cheem-related items<br><br>

  <label for="q8">8. How do you feel when you see someone else with a cheem?</label><br>
  <input type="radio" name="q8" value="a"> Indifferent<br>
  <input type="radio" name="q8" value="b"> A little envious<br>
  <input type="radio" name="q8" value="c"> Happy for them<br>
  <input type="radio" name="q8" value="d"> Overwhelmed with jealousy<br><br>
  
  <label for="q9">9. Have you ever donated money to a cheem-related cause?</label><br>
  <input type="radio" name="q9" value="a"> No<br>
  <input type="radio" name="q9" value="b"> Yes, a small amount<br>
  <input type="radio" name="q9" value="c"> Yes, a moderate amount<br>
  <input type="radio" name="q9" value="d"> Yes, a large amount<br><br>

  <label for="q10">10. How much do you enjoy learning about cheems?</label><br>
  <input type="radio" name="q10" value="a"> Not at all<br>
  <input type="radio" name="q10" value="b"> A little bit<br>
  <input type="radio" name="q10" value="c"> Moderately<br>
  <input type="radio" name="q10" value="d"> Extremely<br><br>
  
  <label for="q11">11. Have you ever participated in a cheem-related event or activity?</label><br>
  <input type="radio" name="q11" value="a"> No<br>
  <input type="radio" name="q11" value="b"> Yes, once<br>
  <input type="radio" name="q11" value="c"> Yes, a few times<br>
  <input type="radio" name="q11" value="d"> Yes, many times<br><br>
  
  <label for="q12">12. Do you have any strong feelings about cheems one way or the other?</label><br>
  <input type="radio" name="q12" value="a"> No<br>
  <input type="radio" name="q12" value="b"> I dislike cheems<br>
  <input type="radio" name="q12" value="c"> I am neutral about cheems<br>
  <input type="radio" name="q12" value="d"> I love cheems<br><br>
  
  <input type="button" value="Submit" onclick="scoreQuiz()">
</form>


<div id="result"></div>

<script type="text/javascript">
function scoreQuiz() {
  var score = 0;
  var form = document.getElementById("cheem-quiz");
  
  for (var i = 0; i < form.length; i++) {
    var input = form[i];
    if (input.type === "radio" && input.checked) {
      score += input.value === "a" ? 0 :
               input.value === "b" ? 1 :
               input.value === "c" ? 2 :
               input.value === "d" ? 3 :
               0;
    }
  }
  
  var resultDiv = document.getElementById("result");
  if (score === 0) {
    resultDiv.innerHTML = "You do not seem to like cheems very much.";
  } else if (score < 15) {
    resultDiv.innerHTML = "You have a moderate level of appreciation for cheems.";
  } else if (score < 30) {
    resultDiv.innerHTML = "You have a strong fondness for cheems.";
  } else {
    resultDiv.innerHTML = "You are obsessed with cheems!";
  }
}
</script>