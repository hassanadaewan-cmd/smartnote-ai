<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>SmartNote AI</title>

<style>

body {
    font-family: Arial, sans-serif;
    background: #ffeaf4;
    margin: 0;
    padding: 20px;
}

.container {
    max-width: 700px;
    margin: auto;
    background: white;
    padding: 25px;
    border-radius: 20px;
}

h1 {
    text-align: center;
    color: #e85d9e;
}

p {
    color: #555;
}

textarea {
    width: 100%;
    height: 250px;
    box-sizing: border-box;
    padding: 15px;
    border: 2px solid #f3b5d0;
    border-radius: 15px;
    font-size: 16px;
}

button {
    width: 100%;
    padding: 15px;
    margin-top: 15px;
    border: none;
    border-radius: 15px;
    background: #e85d9e;
    color: white;
    font-size: 18px;
}

.result {
    margin-top: 20px;
    padding: 15px;
    background: #fff4f9;
    border-radius: 15px;
}

</style>
</head>

<body>

<div class="container">

<h1>🌸 SmartNote AI</h1>

<p>ระบบช่วยสรุปบทเรียน</p>

<textarea id="lesson"
placeholder="ใส่เนื้อหาที่เรียนตรงนี้..."></textarea>

<button onclick="summarize()">
✨ สรุปเนื้อหา
</button>

<div class="result" id="result">
<h2>📚 ผลสรุป</h2>
<p>ผลสรุปจะแสดงตรงนี้</p>
</div>

</div>

<script>

function summarize() {

    let text = document.getElementById("lesson").value;

    if (text.trim() === "") {
        alert("กรุณาใส่เนื้อหาก่อนนะ 💗");
        return;
    }

    let sentences = text
        .split(/[.!?。！？\n]/)
        .map(x => x.trim())
        .filter(x => x.length > 0);

    let summary = sentences.slice(0, 8);

    let html = "<h2>📚 ผลสรุป</h2><ul>";

    summary.forEach(function(item) {
        html += "<li>" + item + "</li>";
    });

    html += "</ul>";

    document.getElementById("result").innerHTML = html;
}

</script>

</body>
</html>
