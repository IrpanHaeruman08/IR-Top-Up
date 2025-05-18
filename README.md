<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>IR Top Up - Diamond Game</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #f5f5f5;
    }
    header {
      background-color: #2d2d2d;
      color: #fff;
      padding: 15px 20px;
      text-align: center;
    }
    .container {
      max-width: 600px;
      margin: 20px auto;
      background: #fff;
      padding: 20px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      border-radius: 8px;
    }
    h1 {
      text-align: center;
      font-size: 20px;
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-top: 15px;
      font-weight: bold;
    }
    input, select, button {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      background-color: #0099ff;
      color: white;
      border: none;
      margin-top: 20px;
      cursor: pointer;
      font-weight: bold;
    }
    button:hover {
      background-color: #007acc;
    }
    footer {
      text-align: center;
      font-size: 14px;
      padding: 10px;
      color: #888;
    }
  </style>
</head>
<body>

<header>
  <h2>IR Top Up | Beli Diamond Game Cepat & Murah</h2>
</header>

<div class="container">
  <h1>Formulir Pembelian Diamond</h1>

  <form id="orderForm">
    <label for="game">Pilih Game</label>
    <select id="game" required>
      <option value="">-- Pilih Game --</option>
      <option value="ff">Free Fire</option>
      <option value="ml">Mobile Legends</option>
      <option value="pubg">PUBG Mobile</option>
    </select>

    <label for="id">Masukkan ID Pemain</label>
    <input type="text" id="id" placeholder="Contoh: 123456789" required>

    <label for="jumlah">Jumlah Diamond</label>
    <select id="jumlah" required></select>

    <label for="pembayaran">Metode Pembayaran</label>
    <select id="pembayaran" required>
      <option value="">-- Pilih Pembayaran --</option>
      <option value="dana">DANA</option>
      <option value="gopay">GoPay</option>
      <option value="qris">QRIS</option>
      <option value="cash">Cash</option>
      <option value="cicil">Cicil</option>
    </select>

    <label for="kontak">Nomor WhatsApp Aktif</label>
    <input type="text" id="kontak" placeholder="Contoh: 081234567890" required>

    <button type="submit">Kirim Pesanan</button>
  </form>
</div>

<footer>
  &copy; 2025 IR Top Up All rights reserved.
</footer>

<script>
  const diamondOptions = {
    ff: [
      { value: "5", text: "5 Diamond - Rp. 1.000" },
      { value: "12", text: "12 Diamond - Rp. 2.500" },
      { value: "50", text: "50 Diamond - Rp. 8.000" },
      { value: "70", text: "70 Diamond - Rp. 10.000" },
      { value: "140", text: "140 Diamond - Rp. 20.000" },
      { value: "355", text: "355 Diamond - Rp. 48.000" },
      { value: "720", text: "720 Diamond - Rp. 95.000" }
    ],
    ml: [
      { value: "86", text: "86 Diamond - Rp20.000" },
      { value: "172", text: "172 Diamond - Rp39.000" },
      { value: "257", text: "257 Diamond - Rp58.000" }
    ],
    pubg: [
      { value: "86", text: "86 Diamond - Rp20.000" },
      { value: "172", text: "172 Diamond - Rp39.000" },
      { value: "257", text: "257 Diamond - Rp58.000" }
    ]
  };

  const gameSelect = document.getElementById("game");
  const jumlahSelect = document.getElementById("jumlah");

  gameSelect.addEventListener("change", function () {
    const selectedGame = this.value;
    jumlahSelect.innerHTML = "<option value=''>-- Pilih Jumlah --</option>";
    if (diamondOptions[selectedGame]) {
      diamondOptions[selectedGame].forEach(option => {
        const opt = document.createElement("option");
        opt.value = option.value;
        opt.textContent = option.text;
        jumlahSelect.appendChild(opt);
      });
    }
  });

  document.getElementById("orderForm").addEventListener("submit", function(e) {
    e.preventDefault();

    const game = gameSelect.value;
    const id = document.getElementById("id").value;
    const jumlah = jumlahSelect.options[jumlahSelect.selectedIndex].text;
    const pembayaran = document.getElementById("pembayaran").value;
    const kontak = document.getElementById("kontak").value;

    const pesan = `Halo IR Top Up,%0ASaya ingin membeli Diamond:%0A- Game: ${game.toUpperCase()}%0A- ID: ${id}%0A- Jumlah: ${jumlah}%0A- Pembayaran: ${pembayaran.toUpperCase()}%0A- Kontak: ${kontak}`;
    window.open(`https://wa.me/6283835926395?text=${pesan}`, "_blank");
  });
</script>

</body>
</html>
