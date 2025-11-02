# SGMC-VOTING-
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Vote for SGMC — Get Rewards!</title>
  <style>
    :root{--accent:#0066ff;--bg:#0f1724;--card:#0b1220;--muted:#9aa4b2}
    body{font-family:Inter,system-ui,Segoe UI,Arial;margin:0;background:linear-gradient(180deg,#071025 0%,#07172d 100%);color:#e6eef6;min-height:100vh;display:flex;align-items:center;justify-content:center;padding:24px}
    .wrap{width:100%;max-width:900px}
    header{display:flex;align-items:center;gap:16px;margin-bottom:18px}
    .logo{width:64px;height:64px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#8b5cf6);display:flex;align-items:center;justify-content:center;font-weight:700}
    .card{background:linear-gradient(180deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));padding:20px;border-radius:12px;box-shadow:0 6px 30px rgba(2,6,23,0.6)}
    h1{margin:0;font-size:20px}
    p.lead{color:var(--muted);margin:6px 0 18px}
    .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px}
    .vote-btn{background:#07112a;border:1px solid rgba(255,255,255,0.03);padding:14px;border-radius:10px;cursor:pointer;display:flex;flex-direction:column;gap:8px;align-items:flex-start}
    .vote-btn h3{margin:0;font-size:16px}
    .vote-btn small{color:var(--muted)}
    .actions{display:flex;gap:8px;margin-top:14px}
    .btn{padding:10px 14px;border-radius:8px;border:none;cursor:pointer}
    .btn.primary{background:var(--accent);color:white}
    .note{margin-top:12px;color:var(--muted);font-size:13px}
    .toast{position:fixed;right:20px;bottom:20px;background:#07112a;padding:12px;border-radius:8px;border:1px solid rgba(255,255,255,0.03);display:none}
    @media (max-width:520px){header{gap:12px}.logo{width:52px;height:52px}}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="logo">SG</div>
      <div>
        <h1>SGMC — Vote & Earn Rewards</h1>
        <p class="lead">Vote for SGMC on the sites below — get coins, keys, and hearts! You can vote every 24 hours on each site.</p>
      </div>
    </header>

    <div class="card">
      <div class="grid" id="sites">
        <!-- duplicate this block for each vote site -->
        <div class="vote-btn" data-link="VOTE_LINK_1">
          <h3>Minecraft-Server-List</h3>
          <small>Vote once every 24 hours • Reward: 1000 coins + 1 Rare Key</small>
          <div class="actions">
            <button class="btn primary" onclick="openVote(this)">Vote</button>
            <button class="btn" onclick="copyLink(this)">Copy Link</button>
          </div>
        </div>

        <div class="vote-btn" data-link="VOTE_LINK_2">
          <h3>MinecraftServers.org</h3>
          <small>Vote once every 24 hours • Reward: +1 Heart</small>
          <div class="actions">
            <button class="btn primary" onclick="openVote(this)">Vote</button>
            <button class="btn" onclick="copyLink(this)">Copy Link</button>
          </div>
        </div>

        <div class="vote-btn" data-link="VOTE_LINK_3">
          <h3>TopG</h3>
          <small>Vote once every 24 hours • Reward: 1 Rare Key</small>
          <div class="actions">
            <button class="btn primary" onclick="openVote(this)">Vote</button>
            <button class="btn" onclick="copyLink(this)">Copy Link</button>
          </div>
        </div>

        <div class="vote-btn" data-link="VOTE_LINK_4">
          <h3>PlanetMinecraft</h3>
          <small>Vote once every 24 hours • Reward: 1000 coins</small>
          <div class="actions">
            <button class="btn primary" onclick="openVote(this)">Vote</button>
            <button class="btn" onclick="copyLink(this)">Copy Link</button>
          </div>
        </div>
      </div>

      <p class="note">After voting: join the server <strong>SGMC (SGMC_SERVER_IP)</strong> and use <code>/voteclaim</code> if required, or the server will auto-detect votes if you have NuVotifier + VotingPlugin configured.</p>
    </div>
  </div>

  <div id="toast" class="toast"></div>

  <script>
    function showToast(text){
      const t = document.getElementById('toast');
      t.innerText = text;
      t.style.display = 'block';
      clearTimeout(t._h);
      t._h = setTimeout(()=> t.style.display = 'none',2500);
    }

    function openVote(btn){
      const item = btn.closest('.vote-btn');
      const url = item.dataset.link;
      if(!url || url.includes('VOTE_LINK')){
        showToast('Replace placeholder VOTE_LINK_x with your real vote URL in the HTML.');
        return;
      }
      window.open(url, '_blank');
      showToast('Thanks for supporting SGMC! Remember to return to server to claim rewards.');
    }

    function copyLink(btn){
      const item = btn.closest('.vote-btn');
      const url = item.dataset.link;
      navigator.clipboard?.writeText(url).then(()=> showToast('Link copied to clipboard'));
    }
  </script>
</body>
</html>

Vote here and get amazing rewards 
