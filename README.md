<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Hisham Keyboard</title>
<style>
body {
  background: #101522;
  color: white;
  font-family: Arial;
  text-align: center;
  padding: 15px;
}
h1 { color: #00e5ff; }
textarea {
  width: 95%;
  height: 100px;
  font-size: 22px;
  border-radius: 12px;
  padding: 10px;
}
.keyboard {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 6px;
  margin-top: 20px;
}
button {
  background: #26354d;
  color: white;
  border: none;
  border-radius: 9px;
  padding: 15px 3px;
  font-size: 20px;
}
button:active { background: #00bcd4; }
.space { grid-column: span 4; }
</style>
</head>
<body>

<h1>⌨️ HISHAM KEYBOARD</h1>
<p>لوحة مفاتيح هشام الخاصة</p>

<textarea id="txt" placeholder="اكتب هنا..."></textarea>

<div class="keyboard" id="keyboard"></div>

<script>
const keys = "ضصثقفغعهخحجدشسيبلاتنمكطئءؤرلاىةوزظذ";
const board = document.getElementById("keyboard");

[...keys].forEach(key => {
 let b = document.createElement("button");
 b.textContent = key;
 b.onclick = () => document.getElementById("txt").value += key;
 board.appendChild(b);
});

function add(label, value) {
 let b = document.createElement("button");
 b.textContent = label;
 b.onclick = () => {
 let t = document.getElementById("txt");
 if(value === "DEL") t.value = t.value.slice(0,-1);
 else t.value += value;
 };
 board.appendChild(b);
}
add("مسافة"," ");
add("⌫","DEL");
add("❤️","❤️");
</script>

</body>
</html>