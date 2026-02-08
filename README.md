<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For My Gauri 💖</title>

<style>
body{
    margin:0;
    font-family:'Comic Sans MS', cursive;
    background:linear-gradient(135deg,#ff6a88,#ff99ac);
    color:white;
    text-align:center;
    overflow-x:hidden;
}
h1{margin-top:25px;font-size:2.5em;}
.card{
    background:rgba(255,255,255,0.2);
    padding:25px;
    margin:30px auto;
    width:88%;
    max-width:650px;
    border-radius:25px;
    box-shadow:0 10px 25px rgba(0,0,0,0.25);
    animation:slideUp 1.2s ease;
}
input{
    padding:10px;
    border-radius:15px;
    border:none;
    width:70%;
    text-align:center;
    font-size:16px;
}
button{
    padding:12px 24px;
    font-size:16px;
    border:none;
    border-radius:30px;
    cursor:pointer;
    background:#ff2e63;
    color:white;
    margin:12px;
    transition:.3s;
    position:relative;
}
button:hover{transform:scale(1.08);}
.hidden{display:none;}

@keyframes slideUp{
    from{transform:translateY(40px);opacity:0}
    to{transform:translateY(0);opacity:1}
}

.ring{
    font-size:65px;
    animation:ring 2s infinite;
}
@keyframes ring{
    0%{transform:scale(1)}
    50%{transform:scale(1.25) rotate(12deg)}
    100%{transform:scale(1)}
}

.proposal, .letter{
    text-align:left;
    line-height:1.7;
    font-size:1.05em;
}

.shayari{
    font-style:italic;
    font-size:1.1em;
    margin-top:20px;
    text-align:center;
}

.heart{
    position:fixed;
    bottom:0;
    font-size:22px;
    animation:float 6s linear infinite;
}
@keyframes float{
    0%{transform:translateY(0);opacity:1}
    100%{transform:translateY(-100vh);opacity:0}
}
</style>
</head>

<body>

<h1>💖 Meri Gauri 💖</h1>

<!-- PASSWORD -->
<div class="card">
    <h2>🔐 Password</h2>
    <p>Your first nickname that I gave you 💕</p>
    <input type="password" id="pass" placeholder="Type here">
    <br>
    <button onclick="checkPass()">Unlock</button>
    <p id="passMsg"></p>
</div>

<!-- DATE PUZZLE -->
<div class="card hidden" id="dateCard">
    <h2>🧩 Yaad Hai?</h2>
    <p>Our proposal date (DD/M/YYYY)</p>
    <input type="text" id="date" placeholder="8/9/2022">
    <br>
    <button onclick="checkDate()">Continue</button>
    <p id="dateMsg"></p>
</div>

<!-- LETTER -->
<div class="card hidden" id="letterCard">
    <h2>💌 Meri Pyaari Gauri</h2>
    <div class="letter">
        Aaj sirf ek din nahi hai…<br>
        aaj woh din hai jab meri zindagi ne khud se wada kiya tha—
        ki agar pyaar karna hai, toh sirf tumse.<br><br>

        Jab tum meri zindagi mein aayi, tab mujhe samajh aaya
        ki pyaar sirf saath rehna nahi hota,
        pyaar woh hota hai jahan dil bina dare apna sab kuch rakh de.
        Tum meri muskaan ban gayi, meri shanti, meri himmat,
        meri sabse khoobsurat aadat.<br><br>

        <b>8/9/2022…</b><br>
        is date ne mujhe sirf tumhara nahi banaya,
        isne mujhe ek behtar insaan banaya.
        Tumne us din mujhe chuna tha,
        aur woh choice meri zindagi ka sabse khoobsurat tohfa ban gayi.<br><br>

        Aaj main phir wahi sawal leke khada hoon,
        thoda zyada pyaar ke saath,
        thoda zyada yakeen ke saath,
        aur poori zindagi ke sapne leke.<br><br>

        Main wada karta hoon—
        main hamesha tumhari izzat karunga,
        tumhare khwabon ko apna samajhunga,
        tumhari khamoshi bhi samajhne ki koshish karunga.
        Main perfect nahi hoon,
        lekin mera pyaar tumhare liye hamesha saccha rahega.<br><br>

        Tum jab hansogi, main khush ho jaunga.
        Tum jab thak jaogi, main tumhara sahara banunga.
        Aur jab zindagi mushkil lage,
        toh main tumhara haath kabhi nahi chhodunga.
    </div>

    <div class="shayari">
        Ek tumhe paake aur paana kya hai<br>
        Main ye duniya chhod du, zamana kya hai
    </div>

    <div class="shayari">
        Aap hi ke bina hu kyun bechain<br>
        Aap hi kyun meri zarurat hai<br>
        Wehem itna haseen nahi hota<br>
        Wakayi aap khoobsurat hai
    </div>

    <button onclick="showProposal()">Aage 💖</button>
</div>

<!-- PROPOSAL -->
<div class="card hidden" id="proposalCard">
    <div class="ring">💍</div>
    <p class="proposal">
        Kya tum phir se mujhe chuno gi?<br><br>
        Iss baar sirf boyfriend nahi,<br>
        balki apna life partner,<br>
        apna humsafar,<br>
        apna hamesha ke liye.<br><br>

        Agar tum haan keh do,<br>
        toh main tumhe woh pyaar dikhaunga<br>
        jo sirf lafzon mein nahi,<br>
        har roz, har saans, har pal mehsoos hoga.
    </p>

    <button onclick="yes()">Yes 💖</button>
    <button id="noBtn" onmouseover="run()">No 😜</button>
</div>

<p id="final" class="hidden" style="font-size:1.6em;">
    She said YES 🥺❤️<br>
    Hamesha tumhara,<br>
    <b>Rudra</b>
</p>

<script>
const password="Panda";

function checkPass(){
    let v=document.getElementById("pass").value;
    if(v.toLowerCase()===password.toLowerCase()){
        document.getElementById("dateCard").classList.remove("hidden");
        document.getElementById("passMsg").innerHTML="Unlocked 💖";
    }else{
        document.getElementById("passMsg").innerHTML="Try again 😜";
    }
}
function checkDate(){
    if(document.getElementById("date").value==="8/9/2022"){
        document.getElementById("letterCard").classList.remove("hidden");
        document.getElementById("dateMsg").innerHTML="Perfect 💕";
    }else{
        document.getElementById("dateMsg").innerHTML="You know this date 🤍";
    }
}
function showProposal(){
    document.getElementById("proposalCard").classList.remove("hidden");
}
function run(){
    let b=document.getElementById("noBtn");
    b.style.left=Math.random()*200-100+"px";
    b.style.top=Math.random()*200-100+"px";
}
function yes(){
    document.getElementById("final").classList.remove("hidden");
}
setInterval(()=>{
    let h=document.createElement("div");
    h.className="heart";
    h.innerHTML="❤️";
    h.style.left=Math.random()*100+"vw";
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),6000);
},400);
</script>

</body>
</html>
