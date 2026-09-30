# mms-esports-tournament-
Official MLBB tournament management system for MMS Esports
<!DOCTYPE html>
<html lang="ms">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MMS Esports - System Kejohanan MLBB</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    }

    body {
      background-color: #0b0d12;
      color: #f8fafc;
      padding: 20px;
      display: flex;
      justify-content: center;
    }

    .container {
      width: 100%;
      max-width: 900px;
    }

    .header {
      text-align: center;
      margin-bottom: 30px;
    }

    .header h1 {
      font-size: 26px;
      color: #ef4444;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .header p {
      color: #94a3b8;
      font-size: 14px;
      margin-top: 5px;
    }

    .card {
      background-color: #141721;
      border-radius: 12px;
      padding: 20px;
      margin-bottom: 25px;
      border: 1px solid #1e2330;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    }

    .card h2 {
      font-size: 18px;
      color: #38bdf8;
      margin-bottom: 15px;
      border-bottom: 1px solid #1e2330;
      padding-bottom: 8px;
    }

    .form-group {
      margin-bottom: 15px;
    }

    label {
      display: block;
      font-size: 13px;
      color: #cbd5e1;
      margin-bottom: 6px;
      font-weight: 600;
    }

    input, select {
      width: 100%;
      padding: 12px;
      background-color: #0d0f17;
      border: 1px solid #282d3f;
      border-radius: 8px;
      color: #ffffff;
      font-size: 14px;
      outline: none;
    }

    input:focus, select:focus {
      border-color: #ef4444;
    }

    .btn {
      width: 100%;
      background-color: #ef4444;
      color: white;
      border: none;
      border-radius: 8px;
      padding: 12px;
      font-weight: bold;
      font-size: 15px;
      cursor: pointer;
      transition: 0.2s;
    }

    .btn:hover {
      background-color: #dc2626;
    }

    .btn-secondary {
      background-color: #0284c7;
      margin-top: 10px;
    }

    .btn-secondary:hover {
      background-color: #0369a1;
    }

    .grid-groups {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
      gap: 20px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 10px;
      font-size: 13px;
    }

    th, td {
      border: 1px solid #1e2330;
      padding: 10px;
      text-align: center;
    }

    th {
      background-color: #0d0f17;
      color: #38bdf8;
    }

    .action-btn {
      width: auto;
      padding: 4px 8px;
      font-size: 11px;
      margin: 1px;
      border-radius: 4px;
      cursor: pointer;
      border: none;
      color: white;
    }

    .btn-win { background-color: #16a34a; }
    .btn-draw { background-color: #d97706; }
    .btn-loss { background-color: #dc2626; }

    @media (max-width: 500px) {
      .grid-groups {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

<div class="container">
  <div class="header">
    <h1>MMS ESPORTS TOURNAMENT</h1>
    <p>Sistem Pendaftaran & Pengurusan Poin Kumpulan A-D</p>
  </div>

  <!-- BORANG PENDAFTARAN -->
  <div class="card">
    <h2>1. Pendaftaran Pasukan</h2>
    <form id="regForm">
      <div class="form-group">
        <label for="teamName">Nama Pasukan:</label>
        <input type="text" id="teamName" required placeholder="Contoh: Kinabatangan Player">
      </div>
      <div class="form-group">
        <label for="captainName">Nama Kapten / WhatsApp:</label>
        <input type="text" id="captainName" required placeholder="Contoh: Mifzal (0178153522)">
      </div>
      <div class="form-group">
        <label for="groupSelect">Pilih Kumpulan:</label>
        <select id="groupSelect">
          <option value="A">Group A</option>
          <option value="B">Group B</option>
          <option value="C">Group C</option>
          <option value="D">Group D</option>
        </select>
      </div>
      <button type="submit" class="btn">Daftarkan Pasukan</button>
    </form>
  </div>

  <!-- PAPARAN KLASEMEN GROUP A, B, C, D -->
  <h2 style="color: #ffffff; margin-bottom: 15px;">2. Carta Kedudukan Kumpulan</h2>
  <div class="grid-groups">
    <!-- GROUP A -->
    <div class="card">
      <h2 style="color: #ef4444;">GROUP A</h2>
      <table id="table-A">
        <thead>
          <tr>
            <th>Pasukan</th>
            <th>M</th>
            <th>S</th>
            <th>K</th>
            <th>Mata</th>
            <th>Aksi</th>
          </tr>
        </thead>
        <tbody></tbody>
      </table>
    </div>

    <!-- GROUP B -->
    <div class="card">
      <h2 style="color: #ef4444;">GROUP B</h2>
      <table id="table-B">
        <thead>
          <tr>
            <th>Pasukan</th>
            <th>M</th>
            <th>S</th>
            <th>K</th>
            <th>Mata</th>
            <th>Aksi</th>
          </tr>
        </thead>
        <tbody></tbody>
      </table>
    </div>

    <!-- GROUP C -->
    <div class="card">
      <h2 style="color: #ef4444;">GROUP C</h2>
      <table id="table-C">
        <thead>
          <tr>
            <th>Pasukan</th>
            <th>M</th>
            <th>S</th>
            <th>K</th>
            <th>Mata</th>
            <th>Aksi</th>
          </tr>
        </thead>
        <tbody></tbody>
      </table>
    </div>

    <!-- GROUP D -->
    <div class="card">
      <h2 style="color: #ef4444;">GROUP D</h2>
      <table id="table-D">
        <thead>
          <tr>
            <th>Pasukan</th>
            <th>M</th>
            <th>S</th>
            <th>K</th>
            <th>Mata</th>
            <th>Aksi</th>
          </tr>
        </thead>
        <tbody></tbody>
      </table>
    </div>
  </div>

  <!-- PAPARAN GRAND FINAL -->
  <div class="card">
    <h2>3. Pasukan Lolos Ke Grand Final (Top 1 Setiap Group)</h2>
    <button class="btn btn-secondary" onclick="updateGrandFinal()">Kemas Kini Senarai Grand Final</button>
    <table id="table-final" style="margin-top: 15px;">
      <thead>
        <tr>
          <th>Asal Group</th>
          <th>Nama Pasukan</th>
          <th>Jumlah Mata</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </div>
</div>

<script>
  // Data simpanan pasukan
  const teams = { A: [], B: [], C: [], D: [] };

  // Handle Borang Pendaftaran
  document.getElementById('regForm').addEventListener('submit', function(e) {
    e.preventDefault();
    const teamName = document.getElementById('teamName').value;
    const group = document.getElementById('groupSelect').value;

    teams[group].push({
      name: teamName,
      win: 0,
      draw: 0,
      loss: 0,
      points: 0
    });

    document.getElementById('regForm').reset();
    renderGroup(group);
  });

  // Fungsi Kemas Kini Skor Perlawanan
  function updateScore(group, index, result) {
    const team = teams[group][index];
    if (result === 'win') team.win += 1;
    if (result === 'draw') team.draw += 1;
    if (result === 'loss') team.loss += 1;
    
    // Formula Mata: Menang = 3, Seri = 1, Kalah = 0
    team.points = (team.win * 3) + (team.draw * 1);

    // Susun mengikut mata tertinggi
    teams[group].sort((a, b) => b.points - a.points);

    renderGroup(group);
  }

  // Papar Data dalam Jadual
  function renderGroup(group) {
    const tbody = document.querySelector(`#table-${group} tbody`);
    tbody.innerHTML = '';

    teams[group].forEach((team, index) => {
      const tr = document.createElement('tr');
      tr.innerHTML = `
        <td><strong>${team.name}</strong></td>
        <td>${team.win}</td>
        <td>${team.draw}</td>
        <td>${team.loss}</td>
        <td><strong style="color:#ef4444;">${team.points}</strong></td>
        <td>
          <button class="action-btn btn-win" onclick="updateScore('${group}', ${index}, 'win')">+M</button>
          <button class="action-btn btn-draw" onclick="updateScore('${group}', ${index}, 'draw')">+S</button>
          <button class="action-btn btn-loss" onclick="updateScore('${group}', ${index}, 'loss')">+K</button>
        </td>
      `;
      tbody.appendChild(tr);
    });
  }

  // Tarik Pasukan Juara Setiap Group ke Grand Final
  function updateGrandFinal() {
    const tbody = document.querySelector('#table-final tbody');
    tbody.innerHTML = '';

    ['A', 'B', 'C', 'D'].forEach(group => {
      if (teams[group].length > 0) {
        const topTeam = teams[group][0]; // Ambil tangga pertama
        const tr = document.createElement('tr');
        tr.innerHTML = `
          <td>Group ${group}</td>
          <td><strong style="color:#38bdf8;">${topTeam.name}</strong></td>
          <td>${topTeam.points} Mata</td>
        `;
        tbody.appendChild(tr);
      }
    });
  }
</script>

</body>
</html>
