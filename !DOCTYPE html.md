<!DOCTYPE html>  
<html lang="el">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>JHON</title>  
  
<style>  
body{  
    margin:0;  
    font-family:-apple-system,BlinkMacSystemFont;  
    background: radial-gradient(circle at top,#121225,#07070c);  
    color:white;  
}  
  
/* HEADER */  
  
.header{  
    text-align:center;  
    padding:20px 10px;  
}  
  
.title{  
    font-size:34px;  
    font-weight:800;  
    letter-spacing:3px;  
    background:linear-gradient(135deg,#ffd86b,#ffffff,#ffb347);  
    -webkit-background-clip:text;  
    -webkit-text-fill-color:transparent;  
    text-transform:uppercase;  
}  
  
.subtitle{  
    font-size:12px;  
    letter-spacing:4px;  
    opacity:0.7;  
    margin-top:6px;  
    color:#ffffff;  
}  
  
/* MONTH BAR */  
.monthBar{  
    display:flex;  
    overflow-x:auto;  
    gap:10px;  
    padding:10px;  
}  
  
.monthBtn{  
    flex-shrink:0;  
    padding:10px 14px;  
    border-radius:999px;  
    background:rgba(255,255,255,0.06);  
}  
  
.monthBtn.active{  
    background:#0a84ff;  
}  
  
/* DAYS */  
.days{  
    display:grid;  
    grid-template-columns:repeat(7,1fr);  
    gap:6px;  
    padding:10px;  
}  
  
.day{  
    height:55px;  
    border-radius:14px;  
    display:flex;  
    align-items:center;  
    justify-content:center;  
    background:rgba(255,255,255,0.05);  
    cursor:pointer;  
}  
  
.day.active{  
    background:#0a84ff;  
}  
  
/* APPOINTMENTS */  
.appointments{  
    padding:10px;  
}  
  
.card{  
    padding:14px;  
    border-radius:18px;  
    margin-top:10px;  
    color:#111;  
    font-weight:600;  
    box-shadow:0 10px 25px rgba(0,0,0,0.4);  
}  
  
/* DELETE */  
.del{  
    margin-top:10px;  
    width:100%;  
    padding:10px;  
    border:none;  
    border-radius:14px;  
    background:rgba(0,0,0,0.3);  
    color:white;  
}  
  
/* FORM */  
.form{  
    margin:10px;  
    padding:15px;  
    border-radius:22px;  
    background:rgba(255,255,255,0.06);  
}  
  
input,select{  
    width:100%;  
    padding:16px;  
    margin-top:10px;  
    border-radius:18px;  
    border:1px solid rgba(255,255,255,0.1);  
    background:rgba(255,255,255,0.06);  
    color:white;  
    font-size:15px;  
    outline:none;  
    backdrop-filter: blur(10px);  
    transition:0.2s;  
}  
  
input:focus, select:focus{  
    border-color:#0a84ff;  
    box-shadow:0 0 12px rgba(10,132,255,0.3);  
    transform:scale(1.02);  
}  
  
button{  
    width:100%;  
    padding:14px;  
    margin-top:10px;  
    border:none;  
    border-radius:999px;  
    background:#0a84ff;  
    color:white;  
    font-weight:600;  
}  
  
/* BUTTON (MAIN ACTION) */  
button{  
    width:100%;  
    padding:16px;  
    margin-top:12px;  
    border:none;  
    border-radius:999px;  
    background:linear-gradient(135deg,#0a84ff,#3aa0ff);  
    color:white;  
    font-weight:700;  
    font-size:15px;  
    box-shadow:0 12px 30px rgba(10,132,255,0.35);  
    transition:0.2s;  
}  
  
button:active{  
    transform:scale(0.97);  
}  
  
/* TIME SELECT (iOS STYLE) */  
select{  
    width:100%;  
    padding:14px;  
    margin-top:10px;  
    border-radius:16px;  
    border:none;  
    background:rgba(255,255,255,0.08);  
    color:white;  
    backdrop-filter: blur(10px);  
    font-size:15px;  
}  
  
/* FORM LABEL LOOK */  
h3{  
    margin:5px 0 10px;  
    font-size:16px;  
    opacity:0.9;  
}  
  
.timeGrid{  
    display:grid;  
    grid-template-columns:repeat(3,1fr);  
    gap:10px;  
    margin-top:10px;  
}  
  
.timeChip{  
    height:44px;  
    display:flex;  
    align-items:center;  
    justify-content:center;  
    border-radius:14px;  
    background:rgba(255,255,255,0.08);  
    border:1px solid rgba(255,255,255,0.1);  
    font-weight:600;  
    cursor:pointer;  
    transition:0.2s;  
}  
  
.timeChip:active{  
    transform:scale(0.95);  
}  
  
.timeChip.active{  
    background:#0a84ff;  
    box-shadow:0 0 15px rgba(10,132,255,0.4);  
}  
  
.field{  
    margin-top:10px;  
}  
  
label{  
    font-size:11px;  
    opacity:0.6;  
    letter-spacing:2px;  
}  
  
</style>  
</head>  
  
<body>  
  
<div class="header">  
    <div class="title">JHON</div>  
    <div class="subtitle">MINIMAL LUXURY BARBER</div>  
</div>  
  
<div class="monthBar" id="monthBar"></div>  
<div class="days" id="days"></div>  
<div class="appointments" id="appointments"></div>  
  
<div class="form">  
  
<h3>Νέο Ραντεβού</h3>  
  
<div class="timeGrid" id="timeGrid"></div>  
<input type="hidden" id="time">  
<div class="field">  
  <label>Όνομα</label>  
  <input id="name" type="text">  
</div>  
<div class="field">  
  <label>Τηλέφωνο</label>  
  <input id="phone" type="tel">  
</div>  
  
<button onclick="add()">Προσθήκη</button>  
  
</div>  
  
<script>  
  
/* ================= DATA ================= */  
let data = JSON.parse(localStorage.getItem("data")) || [];  
  
let date = new Date();  
let selectedDate = null;  
  
/* ================= DOM ================= */  
const monthBar = document.getElementById("monthBar");  
const days = document.getElementById("days");  
const appointments = document.getElementById("appointments");  
const time = document.getElementById("time");  
const nameInput = document.getElementById("name");  
const phone = document.getElementById("phone");  
/* ================= PRICE ================= */  
const PRICE = 10;  
  
/* ================= MONTHS ================= */  
const months=[  
"Ιαν","Φεβ","Μαρ","Απρ",  
"Μαι","Ιουν","Ιουλ","Αυγ",  
"Σεπ","Οκτ","Νοε","Δεκ"  
];  
  
/* ================= COLOR SYSTEM (FIXED) ================= */  
function color(seed){  
    const colors = [  
        "#ff6b6b",  
        "#4dabf7",  
        "#51cf66",  
        "#ffd43b",  
        "#845ef7",  
        "#ff922b",  
        "#ff7ab6",  
        "#20c997",  
        "#74c0fc",  
        "#ffa94d"  
    ];  
  
    let x = Math.sin(seed) * 10000;  
    let index = Math.floor((x - Math.floor(x)) * colors.length);  
  
    return colors[index];  
}  
  
/* ================= TIME ================= */  
function buildTime(){  
    time.innerHTML="";  
    for(let h=9;h<=20;h++){  
        for(let m of [0,30]){  
            if(h===20 && m===30) break;  
            let v=`${String(h).padStart(2,"0")}:${String(m).padStart(2,"0")}`;  
            time.innerHTML+=`<option value="${v}">${v}</option>`;  
        }  
    }  
}  
  
/* ================= MONTHS ================= */  
function renderMonths(){  
    monthBar.innerHTML="";  
    months.forEach((m,i)=>{  
        let d=document.createElement("div");  
        d.className="monthBtn";  
        if(i===date.getMonth()) d.classList.add("active");  
  
        d.innerText=m;  
  
        d.onclick=()=>{  
            date.setMonth(i);  
            renderAll();  
        };  
  
        monthBar.appendChild(d);  
    });  
}  
  
/* ================= DAYS ================= */  
  
const weekDays = ["Κυρ","Δευ","Τρι","Τετ","Πεμ","Παρ","Σαβ"];  
  
function renderDays(){  
  
    days.innerHTML="";  
  
    let y = date.getFullYear();  
    let m = date.getMonth();  
  
    let total = new Date(y, m + 1, 0).getDate();  
  
    for(let i = 1; i <= total; i++){  
  
        let full = `${y}-${m+1}-${i}`;  
        let dayOfWeek = new Date(y, m, i).getDay(); // 0-6  
  
        let d = document.createElement("div");  
        d.className = "day";  
  
        d.innerHTML = `  
            <div style="font-size:11px;opacity:0.7">${weekDays[dayOfWeek]}</div>  
            <div style="font-size:18px;font-weight:700">${i}</div>  
        `;  
  
        d.onclick = () => {  
            selectedDate = full;  
  
            document.querySelectorAll(".day").forEach(x =>  
                x.classList.remove("active")  
            );  
  
            d.classList.add("active");  
            renderAppointments();  
        };  
  
        days.appendChild(d);  
    }  
}  
  
/* ================= ADD ================= */  
function add(){  
  
    if(!selectedDate) return alert("Διάλεξε μέρα");  
    if(!time.value || !nameInput.value || !phone.value) return alert("Συμπλήρωσε όλα");  
  
    /* ❌ NO SAME TIME */  
    let exists = data.find(x =>  
        x.date === selectedDate && x.time === time.value  
    );  
  
    if(exists){  
        alert("⛔ Υπάρχει ήδη ραντεβού σε αυτή την ώρα");  
        return;  
    }  
  
    data.push({  
    id: Date.now(),  
    date: selectedDate,  
    time: time.value,  
    name: nameInput.value,  
    phone: phone.value,  
    price: PRICE  
});  
  
    localStorage.setItem("data",JSON.stringify(data));  
  
    renderAppointments();  
}  
  
/* ================= DELETE ================= */  
function del(id){  
    data = data.filter(x=>x.id!==id);  
    localStorage.setItem("data",JSON.stringify(data));  
    renderAppointments();  
}  
  
/* ================= APPOINTMENTS ================= */  
  
function renderAppointments(){  
  
    appointments.innerHTML = "";  
  
    let dayData = data  
        .filter(x => x.date === selectedDate)  
        .sort((a,b) => a.time.localeCompare(b.time));  
  
    let total = dayData.reduce((sum, x) => sum + (x.price || 0), 0);  
  
    // 💰 ΣΥΝΟΛΟ ΗΜΕΡΑΣ  
    appointments.innerHTML += `  
    <div style="  
        padding:12px;  
        margin-bottom:10px;  
        border-radius:14px;  
        background:rgba(255,255,255,0.08);  
        font-weight:700;  
    ">  
        💰 Σύνολο ημέρας: ${total}€  
    </div>  
    `;  
  
    // 📅 ΡΑΝΤΕΒΟΥ  
    dayData.forEach(a => {  
  
        appointments.innerHTML += `  
        <div class="card" style="background:${color(a.id + a.time.length + a.name.length)}">  
  
            ⏰ ${a.time}<br>  
            👤 ${a.name}<br>  
            📞 ${a.phone}<br>  
            💰 ${a.price}€  
  
            <button class="del" onclick="del(${a.id})">  
                Διαγραφή  
            </button>  
  
        </div>`;  
    });  
}  
  
/* ================= INIT ================= */  
function renderAll(){  
    renderMonths();  
    renderDays();  
    appointments.innerHTML="";  
}  
  
buildTime();  
renderAll();  
  
function buildTime(){  
    const grid = document.getElementById("timeGrid");  
    const timeInput = document.getElementById("time");  
  
    grid.innerHTML = "";  
  
    for(let h = 9; h <= 20; h++){  
        for(let m of [0, 30]){  
  
            if(h === 20 && m === 30) break;  
  
            let t = `${String(h).padStart(2,"0")}:${String(m).padStart(2,"0")}`;  
  
            let div = document.createElement("div");  
            div.className = "timeChip";  
            div.innerText = t;  
  
            div.onclick = () => {  
                document.querySelectorAll(".timeChip").forEach(x=>{  
                    x.classList.remove("active");  
                });  
  
                div.classList.add("active");  
                timeInput.value = t;  
            };  
  
            grid.appendChild(div);  
        }  
    }  
}  
  
</script>  
  
</body>  
</html>  
