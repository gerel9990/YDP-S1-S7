
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Та тархиныхаа аль талыг илүү сайн ашигладаг вэ?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f9f9f9;
            color: #1b7135;
        }
        h1 {
            color: #2c3e50;
            text-align: center;
        }
      form {
        max-width: 600px;
        margin: 0 auto;
        background: #ffffff;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      }
      .question {
      margin-bottom: 20px;
    }
    .question p {
      margin: 10px 0;
    }
    .result {
      font-weight: bold;
      margin-top: 20px;
      text-align: center;
      color: #444;
    }
    .error {
      color: red;
      font-weight: bold;
    }
    button {
      display: block;
      width: 100%;
      padding: 10px;
      margin-top: 20px;
      background-color: #007BFF;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover {
      background-color: #0056b3;
    }
   
    
</style>
</head>
<body>
    <h1>Та тархиныхаа аль талыг илүү сайн ашигладаг вэ?</h1>
    <form id="quizForm">
     
        <div class="question">
            <p><b>1. Ахлах сургуульд байхдаа ямар хичээлүүдэд илүү дуртай байсан бэ?</b></p>
            <label><input type="radio" name="q1" value="A"> А. Монгол хэл, зураг, нийгэм г.м</label><br>
            <label><input type="radio" name="q1" value="B"> Б. Математикийн төрлийн хичээлүүдэд</label><br>
           </div>

           <div class="question">
            <p><b>2. Ямар төрлийн спортоор хичээллэх дуртай вэ?</b></p>
            <label><input type="radio" name="q2" value="A"> А. Ганц хүний спорт</label><br>
            <label><input type="radio" name="q2" value="B"> Б. Багийн спорт</label><br>
           </div>   

           <div class="question">
            <p><b>3. Зүүдэлсэн зүүдээ хэр хугацаанд санадаг вэ?</b></p>
            <label><input type="radio" name="q3" value="A"> А. Үе үе</label><br>
            <label><input type="radio" name="q3" value="B"> Б. Хаяа л эсвэл огт санадаггүй</label><br>
           </div>  

           <div class="question">
            <p><b>4. Ярьж байх үедээ гар болон нүүрний хөдөлгөөнийг хэр их хэрэглэдэг вэ?</b></p>
            <label><input type="radio" name="q4" value="A"> А. Маш их хэрэглэдэг</label><br>
            <label><input type="radio" name="q4" value="B"> Б. Бараг хэрэглэдэггүй</label><br>
           </div>

           <div class="question">
            <p><b>5. Хоёр гараа хуруунуудаа зөрүүлэн барина уу. Аль гарын чинь эрхий хуруу дээр нь
                гарсан байна вэ?</b></p>
            <label><input type="radio" name="q5" value="A"> А. Баруун</label><br>
            <label><input type="radio" name="q5" value="B"> Б. Зүүн</label><br>
           </div>

           <div class="question">
            <p><b>6. Яг одоо цаг хэд болж байгааг баримжаалан хэлнэ үү! Цагаа хараад үзтэл хэр их
                зөрсөн байна вэ?</b></p>
            <label><input type="radio" name="q6" value="A"> А. 10 минутаас их</label><br>
            <label><input type="radio" name="q6" value="B"> Б. 10 минутаас бага</label><br>
           </div>

           <div class="question">
            <p><b>7. Доорхиос алийг нь илүү эргэж амархан санадаг вэ?</b></p>
            <label><input type="radio" name="q7" value="A"> А. Хүмүүсийн царайг</label><br>
            <label><input type="radio" name="q7" value="B"> Б. Хүмүүсийн нэрийг</label><br>
           </div>

           <div class="question">
            <p><b>8. Хоёр нүдээ харж байхдаа харандаагаа хаалганы ирмэгтэй эсвэл цонхны
                ирмэгтэй тэнцүүл. Дараа нь нүдээ зүүн баруун ээлжлэн аниад үз. Аль нүдээ
                анихад харандаа бага хөдөлж байна вэ?</b></p>
            <label><input type="radio" name="q8" value="A"> А. Зүүн нүдээ анихад</label><br>
            <label><input type="radio" name="q8" value="B"> Б. Баруун нүдээ анихад</label><br>
           </div>


        <button type="button" onclick="calculateResult()">Үр дүн</button>
    </form>

    <script>
  function calculateResult() {
  const form = document.getElementById('quizForm');
  const answers = new FormData(form);
  const counts = { A: 0, B: 0 };
  let allAnswered = true;

  for (let i = 1; i <= 8; i++) {
    if (!answers.has('q' + i)) {
      allAnswered = false;
      break;
    }
  }

  if (!allAnswered) {
     document.getElementById('result').innerText = "Та бүх асуултад хариулна уу.";
            return;
  }  
  for (let value of answers.values()) {
    counts[value]++;
  }
  let result = "";
  if (counts.A >= 4) {
 result = `<b>Баруун тархи</b> <br><br>
        <ul>
            <li> -Бүтээлч сэтгэхүй сайтай</li>
            <li> -Мөрөөдөмтгий</li>
            <li> -Сонссоноо мартдаггүй</li>
            <li> -Мэдрэмж өндөртэй</li>
            <il> -Үнэрлэх, амтлах нь маш чухал</li>
            <il> -Хэсэгчлэн биш бүтнээр нь тусгадаг</li>
            <il> -Дотоод мэдрэмжээ их ашигладаг</li>
            <il> -Субьектив</li>
            <il> -Аливаад сэтгэл хөдлөлөөрөө хөдөлдөг</li>
        </ul>`;
  }
  else if (counts.B >= 4) {
    result = `<b>Зүүн тархи</b> <br><br>
        <ul>
            <li> -Логик сэтгэхүй сайтай</li>
            <li> -Ангилах, нэрлэх, дарааллуулах, хүснэгтлэх, задлан шинжлэх чадвартай</li>
            <li> -Математикийн үйлдлүүдийг сайн хийдэг</li>
            <li> -Үг хэллэгийг шууд утгаар нь хэрэглэдэг</li>
            <li> -Нарийн төвөгтэй зүйлүүдийг сайн олж хардаг</li>
            <li> -Бүтнээр биш хэсэгчлэн тусгадаг</li>
            <li> -Системтэй дэг журамтай ажилладаг</li>
            <li> -Объектив</li>
            <li> -Аливаад бодитой ханддаг</il>
        </ul>`;
  }
  else {
    result = `
      <h1>Таны хоёр тархи тэнцвэртэй ажилладаг байх нь.</h1>`;
 if (counts.A < 4 && counts.B < 4) {
      const newWindow = window.open("", "_blank");
      newWindow.document.write(`
        <html>
        <head>
            <title>Үр дүн</title>
            <style>
                body { font-family: Arial, sans-serif; margin: 20px; background-color: #f9f9f9; color: #333; text-align: center; }
                h1 { color: #2c3e50; }
                ul { text-align: left; display: inline-block; margin: 0 auto; padding: 0; list-style-type: none; }
                li { margin-bottom: 10px; }
            </style>
        </head>
        <body>
            ${result}
        </body>
        </html>
      `);
      newWindow.document.close();
    } else {
      document.getElementById('result').innerHTML = result;
    }
  }
    </script>
    <div id="result" class="result"></div>
</body>
</html>  
