---
layout: default
title: Page 2 Example (Variable Check Grader)
---

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "game_running=True\n" +
    "while game_running:\n" +
    "  code = \"2341\"\n" +
    "  no_of_guesses=0\n" +
    "  guess=input(\"Enter your guess:\")\n" +
    "  no_of_guesses +=1\n" +
    "  if guess == code:\n" +
    "    print(\"Well done you guessed the code\")\n" +
    "    game_running=False\n" +
    "  else:\n" +
    "    for i in range (len(guess)):\n" +
    "      if guess[i]==code[i]:\n" +
    "        i+=1\n" +
    "        print(\"Position \"+str(i)+\" correct\")\n" +
    "      else:\n" +
    "        pass";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>


[Next](./example2.html)
