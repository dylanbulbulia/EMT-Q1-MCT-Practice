<!DOCTYPE html>
<html>
<head>
    <title>EMS Cognitive Evaluation Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f4f4f4;
        }
        .quiz-container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            max-width: 800px;
            margin: auto;
        }
        .question {
            margin-bottom: 10px;
            font-size: 18px;
        }
        .options label {
            display: block;
            margin: 5px 0;
        }
        .submit-btn {
            margin-top: 10px;
            padding: 10px;
            background: #007bff;
            color: white;
            border: none;
            cursor: pointer;
            font-size: 16px;
        }
        .result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <h2>EMS Cognitive Evaluation Quiz</h2>
        <form id="quizForm">
            
            <script>
                const questions = [
                    { q: "What should an EMT candidate do if they have been convicted of a felony or misdemeanor?", a: "b", options: ["Ignore it, as it won't affect certification.", "Disclose it to the certifying agency.", "Only mention it if asked directly.", "Appeal directly to the EMS board."] },
                    { q: "Why are EMRs an important part of the EMS system?", a: "a", options: ["They're often the first on scene and provide immediate care.", "They replace EMTs in many situations.", "They provide advanced cardiac life support.", "They handle only administrative tasks."] },
                    { q: "What skills would a layperson be trained in?", a: "d", options: ["Advanced airway management", "Drug administration", "Surgical interventions", "Basic First Aid, CPR, AED use"] },
                    { q: "What is the EMS medical director responsible for?", a: "c", options: ["Operating ambulances.", "Providing financial oversight.", "Overseeing medical protocols and patient care quality.", "Scheduling EMT shifts."] },
                    { q: "What is ventilation?", a: "c", options: ["Blood circulation", "Gas exchange in tissues", "Mechanical air movement in lungs", "Oxygen transport in blood"] },
                    { q: "How often should an unstable patient be reassessed?", a: "c", options: ["Every 30 minutes", "Every 10 minutes", "Every 5 minutes", "Every 20 minutes"] },
                    { q: "What does BLS stand for?", a: "d", options: ["Basic Lung Support", "Blood Loss Syndrome", "Brain Life Safety", "Basic Life Support"] },
                    { q: "What should you do first with an unresponsive patient?", a: "a", options: ["Check for responsiveness", "Start CPR immediately", "Administer oxygen", "Check blood pressure"] },
                    { q: "Which device should be used when transporting a patient down a staircase?", a: "c", options: ["Backboard", "Stretcher", "Stair Chair", "Traction splint"] },
                    { q: "What does diaphoretic mean?", a: "c", options: ["Red skin", "Cold extremities", "Profuse sweating", "Pale skin"] },
                    { q: "Why can a pulse be felt in a patient?", a: "a", options: ["It is a pressure wave from heart contractions", "It is caused by muscle movement", "It is due to air moving through arteries", "It is only present when a person is in shock"] },
                    { q: "What is the best way to lift a patient using a power grip?", a: "d", options: ["Bend at the back", "Lift with your arms", "Keep feet close together", "Lift with legs and keep back straight"] },
                    { q: "What is the role of red blood cells?", a: "c", options: ["Fighting infection", "Clotting blood", "Transporting oxygen", "Producing hormones"] },
                    { q: "Which part of the spine is located between the lumbar and coccyx?", a: "b", options: ["Thoracic", "Sacral", "Cervical", "Medial"] },
                    { q: "What is the primary function of the spinal cord?", a: "c", options: ["Produce hormones", "Pump blood", "Transmit nerve signals", "Filter waste"] }
                ];
                
                while (questions.length < 50) {
                    questions.push({
                        q: "Placeholder Question "+(questions.length+1),
                        a: "a",
                        options: ["Option 1", "Option 2", "Option 3", "Option 4"]
                    });
                }
                
                let quizHtml = "";
                questions.forEach((question, index) => {
                    quizHtml += `<div class='question'><p>${index + 1}. ${question.q}</p>`;
                    question.options.forEach((option, i) => {
                        quizHtml += `<label><input type='radio' name='q${index}' value='${String.fromCharCode(97 + i)}'> ${option}</label>`;
                    });
                    quizHtml += "</div>";
                });
                
                document.write(`<div class='quiz-container'><form id='quizForm'>${quizHtml}<button type='button' class='submit-btn' onclick='checkAnswers()'>Submit Answers</button><p class='result' id='result'></p></form></div>`);
                
                function checkAnswers() {
                    let score = 0;
                    questions.forEach((question, index) => {
                        let selected = document.querySelector(`input[name='q${index}']:checked`);
                        if (selected && selected.value === question.a) {
                            score++;
                        }
                    });
                    document.getElementById('result').innerText = `You scored ${score} out of ${questions.length}.`;
                }
            </script>
        </form>
    </div>
</body>
</html>
