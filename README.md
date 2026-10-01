<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>🦋 Savage Zone</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800&display=swap');

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:'Poppins',sans-serif;
    min-height:100vh;
    overflow-x:hidden;
    color:#222;

    background:
    radial-gradient(circle at 20% 10%,#fff 0 3%,transparent 20%),
    radial-gradient(circle at 85% 15%,#ff9fc7 0 4%,transparent 22%),
    radial-gradient(circle at 10% 90%,#ffd3e6 0 5%,transparent 25%),
    linear-gradient(135deg,#ffc1dc,#fff1f7,#ffb9d8);

    background-size:200% 200%;
    animation:bgMove 10s ease infinite;
}

@keyframes bgMove{
    0%{background-position:0% 50%}
    50%{background-position:100% 50%}
    100%{background-position:0% 50%}
}

/* Floating emoji */

.float{
    position:fixed;
    pointer-events:none;
    z-index:0;
    opacity:.75;
    animation:floatUp linear infinite;
}

.f1{left:7%;font-size:25px;animation-duration:8s}
.f2{left:22%;font-size:18px;animation-duration:11s;animation-delay:2s}
.f3{left:78%;font-size:25px;animation-duration:9s;animation-delay:1s}
.f4{left:90%;font-size:17px;animation-duration:12s;animation-delay:3s}
.f5{left:48%;font-size:20px;animation-duration:10s;animation-delay:4s}

@keyframes floatUp{
    0%{
        transform:translateY(110vh) rotate(0deg);
        opacity:0;
    }
    15%{opacity:.8}
    50%{transform:translateY(50vh) rotate(180deg)}
    100%{
        transform:translateY(-10vh) rotate(360deg);
        opacity:0;
    }
}

/* Sparkles */

.sparkle{
    position:fixed;
    color:white;
    animation:twinkle 2s infinite alternate;
    z-index:0;
}

.s1{top:12%;left:12%}
.s2{top:28%;right:12%;animation-delay:.5s}
.s3{top:70%;left:8%;animation-delay:1s}
.s4{bottom:10%;right:18%;animation-delay:1.5s}

@keyframes twinkle{
    from{
        transform:scale(.6);
        opacity:.2;
    }
    to{
        transform:scale(1.5);
        opacity:1;
    }
}

.container{
    position:relative;
    z-index:2;
    width:100%;
    max-width:680px;
    margin:auto;
    padding:28px 15px;
}

/* Header */

.header{
    text-align:center;
    margin-bottom:30px;
}

.logo{
    font-size:43px;
    font-weight:800;
    letter-spacing:3px;

    background:linear-gradient(
        90deg,
        #111,
        #ff3f91,
        #111,
        #ff3f91,
        #111
    );

    background-size:300%;
    -webkit-background-clip:text;
    color:transparent;

    animation:logoGlow 4s linear infinite;
}

@keyframes logoGlow{
    0%{background-position:0%}
    100%{background-position:300%}
}

.subtitle{
    margin-top:5px;
    color:#777;
    font-size:14px;
}

.description{
    display:inline-block;
    margin-top:13px;
    padding:9px 17px;

    border-radius:30px;

    background:rgba(255,255,255,.5);
    border:1px solid rgba(255,255,255,.8);

    backdrop-filter:blur(15px);

    box-shadow:
    0 8px 25px rgba(255,80,150,.12),
    inset 0 1px 2px white;

    color:#555;
    font-size:13px;

    animation:pulse 2.5s infinite;
}

@keyframes pulse{
    0%,100%{transform:scale(1)}
    50%{transform:scale(1.03)}
}

/* Cards */

.card{
    position:relative;
    overflow:hidden;

    padding:22px;
    margin-bottom:18px;

    border-radius:24px;

    background:rgba(255,255,255,.45);
    border:1px solid rgba(255,255,255,.8);

    backdrop-filter:blur(20px);
    -webkit-backdrop-filter:blur(20px);

    box-shadow:
    0 15px 40px rgba(170,50,100,.13),
    inset 0 1px 2px rgba(255,255,255,.9);

    transition:.35s ease;

    animation:cardIn .7s ease both;
}

.card:nth-child(2){animation-delay:.1s}
.card:nth-child(3){animation-delay:.2s}
.card:nth-child(4){animation-delay:.3s}
.card:nth-child(5){animation-delay:.4s}

@keyframes cardIn{
    from{
        opacity:0;
        transform:translateY(25px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

.card:hover{
    transform:translateY(-7px) scale(1.015);

    box-shadow:
    0 20px 50px rgba(255,60,140,.2),
    inset 0 1px 3px white;
}

/* Shine */

.card::before{
    content:"";
    position:absolute;
    top:-100%;
    left:-100%;

    width:50%;
    height:300%;

    background:linear-gradient(
        90deg,
        transparent,
        rgba(255,255,255,.5),
        transparent
    );

    transform:rotate(25deg);
    transition:.7s;
}

.card:hover::before{
    left:150%;
}

/* Card content */

.number{
    font-size:19px;
    font-weight:700;
    margin-bottom:7px;
}

.text{
    color:#666;
    font-size:14px;
    line-height:1.6;
    margin-bottom:16px;
}

/* Buttons */

.btn{
    position:relative;
    overflow:hidden;

    display:inline-flex;
    align-items:center;
    justify-content:center;
    gap:8px;

    padding:11px 20px;

    color:white;
    text-decoration:none;

    border-radius:14px;

    background:linear-gradient(
        135deg,
        #111,
        #333
    );

    font-size:13px;
    font-weight:600;

    box-shadow:
    0 7px 18px rgba(0,0,0,.18);

    transition:.3s ease;
}

.btn::before{
    content:"";
    position:absolute;
    top:0;
    left:-100%;
    width:100%;
    height:100%;

    background:linear-gradient(
        90deg,
        transparent,
        rgba(255,255,255,.35),
        transparent
    );

    transition:.5s;
}

.btn:hover::before{
    left:100%;
}

.btn:hover{
    transform:translateY(-3px) scale(1.04);

    background:linear-gradient(
        135deg,
        #ff3f91,
        #ff7db5
    );

    box-shadow:
    0 10px 25px rgba(255,63,145,.4);
}

/* Footer */

.footer{
    text-align:center;
    margin-top:28px;
    padding-bottom:10px;

    color:#999;
    font-size:12px;
}

.footer span{
    color:#ff4b98;
}

/* Mobile */

@media(max-width:500px){

    .container{
        padding:22px 13px;
    }

    .logo{
        font-size:34px;
        letter-spacing:2px;
    }

    .card{
        padding:19px;
    }

    .number{
        font-size:17px;
    }

    .description{
        font-size:12px;
    }
}
</style>
</head>


<body>

<!-- Floating emojis -->

<div class="float f1">🦋</div>
<div class="float f2">🌸</div>
<div class="float f3">🎀</div>
<div class="float f4">🫧</div>
<div class="float f5">💗</div>

<!-- Sparkles -->

<div class="sparkle s1">✦</div>
<div class="sparkle s2">✧</div>
<div class="sparkle s3">⋆</div>
<div class="sparkle s4">✦</div>


<div class="container">

<header class="header">

    <div class="logo">
        🦋 SAVAGE ZONE
    </div>

    <div class="subtitle">
        𐙚₊˚⊹ Welcome to our little world ⋆｡°✩
    </div>

    <div class="description">
        We need admin/member for our GC! 💗
    </div>

</header>


<!-- GROUP -->

<section class="card">

    <div class="number">
        🦋 1️⃣ Join Our Group
    </div>

    <div class="text">
        আমাদের group-এ add হতে চাইলে নিচের
        দেওয়া link-এ click করো।
    </div>

    <a
      class="btn"
      href="https://tiktok.me/group/ZSqmaVKJK/"
      target="_blank"
      rel="noopener noreferrer"
    >
      🫶 Join Group
    </a>

</section>


<!-- OWNER -->

<section class="card">

    <div class="number">
        👑 2️⃣ Talk With Our Owner
    </div>

    <div class="text">
        আমাদের group-এর Owner-এর সাথে কথা বলতে
        চাইলে নিচের ID-তে message দাও।
    </div>

    <a
      class="btn"
      href="https://www.tiktok.com/@unknown_48397?_r=1&_t=ZS-9ACMZ8x4H24"
      target="_blank"
      rel="noopener noreferrer"
    >
      💌 Message Owner
    </a>

</section>


<!-- GROUP ACCOUNT -->

<section class="card">

    <div class="number">
        🦋 3️⃣ Our Group Account
    </div>

    <div class="text">
        আমাদের official group account দেখতে
        নিচের link-এ click করো।
    </div>

    <a
      class="btn"
      href="https://www.tiktok.com/@savagezone.official?_r=1&_t=ZS-9ACMV6B1z1x"
      target="_blank"
      rel="noopener noreferrer"
    >
      ✨ Visit Group ID
    </a>

</section>


<!-- ADMIN 1 -->

<section class="card">

    <div class="number">
        🐣🖤 4️⃣ Our 1st Admin
    </div>

    <div class="text">
        আমাদের 1st Admin-এর সাথে যোগাযোগ করতে
        নিচের link-এ click করো।
    </div>

    <a
      class="btn"
      href="https://www.tiktok.com/@mariyamoni585?_r=1&_t=ZS-9ACMVM2uuBh"
      target="_blank"
      rel="noopener noreferrer"
    >
      🫠✨Visit Admin
    </a>

</section>


<!-- ADMIN 2 -->

<section class="card">

    <div class="number">
        🥹💗 5️⃣ Our 2nd Admin
    </div>

    <div class="text">
        আমাদের 2nd Admin-এর সাথে যোগাযোগ করতে
        নিচের link-এ click করো।
    </div>

    <a
      class="btn"
      href="https://www.tiktok.com/@mohini____67?_r=1&_t=ZS-9ACMbT91EVa"
      target="_blank"
      rel="noopener noreferrer"
    >
      🌷 Visit Admin
    </a>

</section>


<footer class="footer">
    𐙚₊˚⊹ <span>SAVAGE ZONE</span> • Official GC Page ♡
</footer>

</div>

</body>
</html>
