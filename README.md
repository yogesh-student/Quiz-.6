<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>7-Question Quiz</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f8fb;
      padding: 20px;
      max-width: 700px;
      margin: auto;
    }
    h1 {
      color: #333;
    }
    .question {
      margin-bottom: 20px;
      padding: 10px;
      background: #fff;
      border-radius: 8px;
      box-shadow: 0 0 5px #ccc;
    }
    .options label {
      display: block;
      margin: 5px 0;
    }
    #submitBtn {
      padding: 10px 20px;
      font-size: 16px;
      margin-top: 20px;
      cursor: pointer;
    }
    #result {
      margin-top: 30px;
      padding: 15px;
      background: #e6ffe6;
      border: 2px solid #4CAF50;
      border-radius: 8px;
    }
  </style>
</head>
<body>

  <h1>7-Question Quiz</h1>

  <form id="quizForm">

    <div class="question">
      <p>1. Question 1?</p>
      <div class="options">
        <label><input type="radio" name="q1" value="A"> A. Option A</label>
        <label><input type="radio" name="q1" value="B"> B. Option B</label>
        <label><input type="radio" name="q1" value="C"> C. Option C</label>
        <label><input type="radio" name="q1" value="D"> D. Option D</label>
      </div>
    </div>

    <div class="question">
      <p>2. Question 2?</p>
      <div class="options">
        <label><input type="radio" name="q2" value="A"> A. Option A</label>
        <label><input type="radio" name="q2" value="B"> B. Option B</label>
        <label><input type="radio" name="q2" value="C"> C. Option C</label>
        <label><input type="radio" name="q2" value="D"> D. Option D</label>
      </div>
    </div>

    <div class="question">
      <p>3. Question 3?</p>
      <div class="options">
        <label><input type="radio" name="q3" value="A"> A. Option A</label>
        <label><input type="radio" name="q3" value="B"> B. Option B</label>
        <label><input type="radio" name="q3" value="C"> C. Option C</label>
        <label><input type="radio" name="q3" value="D"> D. Option D</label>
      </div>
    </div>

    <div class="question">
      <p>4. Question 4?</p>
      <div class="options">
        <label><input type="radio" name="q4" value="A"> A. Option A</label>
        <label><input type="radio" name="q4" value="B"> B. Option B</label>
        <label><input type="radio" name="q4" value="C"> C. Option C</label>
        <label><input type="radio" name="q4" value="D"> D. Option D</label>
      </div>
    </div>

    <div class="question">
      <p>5. Question 5?</p>
      <div class="options">
        <label><input type="radio" name="q5" value="A"> A. Option A</label>
        <label><input type="radio" name="q5" value="B"> B. Option B</label>
        <label><input type="radio" name="q5" value="C"> C. Option C</label>
        <label><input type="radio" name="q5" value="D"> D. Option D</label>
      </div>
    </div>

    <div class="question">
      <p>6. Question 6?</p>
      <div class="options">
        <label><input type="radio" name="q6" value="A"> A. Option A</label>
        <label><input type="radio" name="q6" value="B"> B. Option B</label>
        <label><input type="radio" name="q6" value="C"> C. Option C</label>
        <label><input type="radio" name="q6" value="D"> D. Option D</label>
      </div>
    </div>

    <div class="question">
      <p>7. Question 7?</p>
      <div class="options">
        <label><input type="radio" name="q7" value="A"> A. Option A</label>
        <label><input type="radio" name="q7" value="B"> B. Option B</label>
        <label><input type="radio" name="q7" value="C"> C. Option C</label>
        <label><input type="radio" name="q7" value="D"> D. Option D</label>
      </div>
    </div>

    <button type="button" id="submitBtn" onclick="calculateScore()">Submit Quiz</button>

  </form>

  <div id="result"></div>

  <script>
    function calculateScore() {
      const answerKey = ['A', 'B', 'D', 'C', 'C', 'A', 'B'];
      let correct = 0, incorrect = 0, skipped = 0, score = 0;

      for (let i = 1; i <= 7; i++) {
        const options = document.getElementsByName("q" + i);
        let selected = '';
        for (const option of options) {
          if (option.checked) {
            selected = option.value;
            break;
          }
        }

        if (selected === '') {
          skipped++;
          score -= 5;
        } else if (selected === answerKey[i - 1]) {
          correct++;
          score += 7;
        } else {
          incorrect++;
          score -= 8;
        }
      }

      document.getElementById("result").innerHTML = `
        <h3>Scorecard</h3>
        <p>✅ Correct: ${correct}</p>
        <p>❌ Incorrect: ${incorrect}</p>
        <p>⚠️ Skipped: ${skipped}</p>
        <p><strong>🎯 Final Score: ${score}</strong></p>
      `;
    }
  </script>

</body>
</html>
