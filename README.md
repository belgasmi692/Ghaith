# Ghaith
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>اختيار العطر المناسب لك حسب شخصيتك</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #6a1b9a;
            color: white;
            padding: 20px;
            text-align: center;
        }
        .container {
            padding: 20px;
        }
        .question {
            font-size: 20px;
            margin: 20px 0;
        }
        .options {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .option {
            background-color: #e1bee7;
            margin: 5px;
            padding: 15px;
            cursor: pointer;
            border: none;
            text-align: center;
            border-radius: 8px;
        }
        .option:hover {
            background-color: #8e24aa;
            color: white;
        }
        #result {
            display: none;
        }
        #result h2 {
            color: #6a1b9a;
        }
        #result p {
            font-size: 18px;
        }
    </style>
</head>
<body>
    <header>
        <h1>اختيار العطر المناسب لك حسب شخصيتك</h1>
    </header>

    <div class="container">
        <!-- استبيان الأسئلة -->
        <div id="quiz">
            <div class="question">
                ما هو تفضيلك في الحياة؟
            </div>
            <div class="options">
                <button class="option" onclick="nextQuestion(1)">أن أكون نشطًا ومبتهجًا</button>
                <button class="option" onclick="nextQuestion(2)">أن أكون هادئًا ومرتاحًا</button>
            </div>
        </div>

        <!-- عرض النتيجة -->
        <div id="result">
            <h2>نتيجتك:</h2>
            <p id="result-text"></p>
        </div>
    </div>

    <script>
        // متغير لتخزين إجابات المستخدم
        let answers = [];

        // الانتقال إلى السؤال التالي
        function nextQuestion(answer) {
            answers.push(answer); // حفظ الإجابة
            // عرض السؤال التالي أو النتيجة بناءً على الإجابة
            if (answers.length === 1) {
                showResult();
            }
        }

        // عرض النتيجة بناءً على الإجابة
        function showResult() {
            const resultText = document.getElementById('result-text');
            const resultDiv = document.getElementById('result');
            const quizDiv = document.getElementById('quiz');
            
            // إخفاء الاستبيان وعرض النتيجة
            quizDiv.style.display = 'none';
            resultDiv.style.display = 'block';

            // تحديد النتيجة بناءً على الإجابات
            if (answers[0] === 1) {
                resultText.innerHTML = 'شخصيتك تتناسب مع العطور المنعشة والنشيطة مثل العطور الحمضية مثل "دولتشي & غابانا لايت بلو".';
            } else if (answers[0] === 2) {
                resultText.innerHTML = 'شخصيتك تتناسب مع العطور الهادئة والخشبية مثل "شانيل رقم 5".';
            }
        }
    </script>
</body>
</html>