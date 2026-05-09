# tugas6
[tugas 6.html](https://github.com/user-attachments/files/27552365/tugas.6.html)
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Program JavaScript Dasar</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        .program {
            background: white;
            margin: 20px 0;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        h2 {
            color: #2c3e50;
            border-bottom: 3px solid #3498db;
            padding-bottom: 10px;
        }
        input {
            padding: 8px;
            margin: 5px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        button {
            background: #3498db;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background: #2980b9;
        }
        .result {
            margin-top: 15px;
            padding: 15px;
            background: #ecf0f1;
            border-radius: 5px;
            border-left: 4px solid #3498db;
        }
    </style>
</head>
<body>

<!-- 1. Program Biodata -->
<div class="program">
    <h2>1. Program Biodata</h2>
    <input type="text" id="nama" placeholder="Masukkan nama">
    <input type="number" id="umur" placeholder="Masukkan umur">
    <button onclick="biodata()">Tampilkan Biodata</button>
    <div id="biodataResult"></div>
</div>

<!-- 2. Kalkulator Sederhana -->
<div class="program">
    <h2>2. Kalkulator Sederhana</h2>
    <input type="number" id="angka1" placeholder="Angka pertama">
    <input type="number" id="angka2" placeholder="Angka kedua">
    <button onclick="kalkulator()">Hitung</button>
    <div id="kalkulatorResult"></div>
</div>

<!-- 3. Perhitungan Nilai -->
<div class="program">
    <h2>3. Perhitungan Nilai Mahasiswa</h2>
    <input type="number" id="nilai1" placeholder="Nilai 1">
    <input type="number" id="nilai2" placeholder="Nilai 2">
    <input type="number" id="nilai3" placeholder="Nilai 3">
    <button onclick="hitungRataRata()">Hitung Rata-rata</button>
    <div id="rataRataResult"></div>
</div>

<!-- 4. Konversi Suhu -->
<div class="program">
    <h2>4. Konversi Suhu Celsius ke Fahrenheit</h2>
    <input type="number" id="celsius" placeholder="Suhu Celsius" step="0.1">
    <button onclick="konversiSuhu()">Konversi</button>
    <div id="suhuResult"></div>
</div>

<!-- 5. Kasir Sederhana -->
<div class="program">
    <h2>5. Kasir Sederhana</h2>
    <input type="text" id="namaBarang" placeholder="Nama barang">
    <input type="number" id="hargaBarang" placeholder="Harga barang">
    <input type="number" id="jumlahBarang" placeholder="Jumlah barang">
    <button onclick="kasir()">Hitung Total</button>
    <div id="kasirResult"></div>
</div>

<!-- 6. Luas Persegi Panjang -->
<div class="program">
    <h2>6. Luas Persegi Panjang</h2>
    <input type="number" id="panjang" placeholder="Panjang">
    <input type="number" id="lebar" placeholder="Lebar">
    <button onclick="luasPersegi()">Hitung Luas</button>
    <div id="luasResult"></div>
</div>

<script>
    // 1. Program Biodata
    function biodata() {
        const nama = document.getElementById('nama').value;
        const umur = document.getElementById('umur').value;
        
        let result = "<div class='result'>";
        result += "<h3>BIODATA</h3>";
        result += "<p><strong>Nama:</strong> " + nama + "</p>";
        result += "<p><strong>Umur:</strong> " + umur + " tahun</p>";
        result += "</div>";
        
        document.getElementById('biodataResult').innerHTML = result;
    }

    // 2. Kalkulator Sederhana
    function kalkulator() {
        const angka1 = parseFloat(document.getElementById('angka1').value);
        const angka2 = parseFloat(document.getElementById('angka2').value);
        
        if (isNaN(angka1) || isNaN(angka2)) {
            document.getElementById('kalkulatorResult').innerHTML = 
                "<div class='result'>Masukkan dua angka yang valid!</div>";
            return;
        }
        
        const tambah = angka1 + angka2;
        const kurang = angka1 - angka2;
        const kali = angka1 * angka2;
        const bagi = angka2 !== 0 ? (angka1 / angka2).toFixed(2) : "Tidak bisa dibagi nol";
        
        let result = "<div class='result'>";
        result += "<h3>Hasil Perhitungan:</h3>";
        result += "<p><strong>Penjumlahan:</strong> " + angka1 + " + " + angka2 + " = " + tambah + "</p>";
        result += "<p><strong>Pengurangan:</strong> " + angka1 + " - " + angka2 + " = " + kurang + "</p>";
        result += "<p><strong>Perkalian:</strong> " + angka1 + " × " + angka2 + " = " + kali + "</p>";
        result += "<p><strong>Pembagian:</strong> " + angka1 + " ÷ " + angka2 + " = " + bagi + "</p>";
        result += "</div>";
        
        document.getElementById('kalkulatorResult').innerHTML = result;
    }

    // 3. Perhitungan Nilai
    function hitungRataRata() {
        const nilai1 = parseFloat(document.getElementById('nilai1').value);
        const nilai2 = parseFloat(document.getElementById('nilai2').value);
        const nilai3 = parseFloat(document.getElementById('nilai3').value);
        
        if (isNaN(nilai1) || isNaN(nilai2) || isNaN(nilai3)) {
            document.getElementById('rataRataResult').innerHTML = 
                "<div class='result'>Masukkan tiga nilai yang valid!</div>";
            return;
        }
        
        const rataRata = ((nilai1 + nilai2 + nilai3) / 3).toFixed(2);
        
        let result = "<div class='result'>";
        result += "<h3>Hasil Perhitungan Nilai:</h3>";
        result += "<p>Nilai 1: " + nilai1 + "</p>";
        result += "<p>Nilai 2: " + nilai2 + "</p>";
        result += "<p>Nilai 3: " + nilai3 + "</p>";
        result += "<p><strong>Rata-rata:</strong> " + rataRata + "</p>";
        result += "</div>";
        
        document.getElementById('rataRataResult').innerHTML = result;
    }

    // 4. Konversi Suhu
    function konversiSuhu() {
        const celsius = parseFloat(document.getElementById('celsius').value);
        
        if (isNaN(celsius)) {
            document.getElementById('suhuResult').innerHTML = 
                "<div class='result'>Masukkan suhu Celsius yang valid!</div>";
            return;
        }
        
        const fahrenheit = (9/5 * celsius + 32).toFixed(2);
        
        let result = "<div class='result'>";
        result += "<h3>Konversi Suhu:</h3>";
        result += "<p><strong>Celsius:</strong> " + celsius + "°C</p>";
        result += "<p><strong>Fahrenheit:</strong> " + fahrenheit + "°F</p>";
        result += "<p><em>Rumus: F = (9/5 × C) + 32</em></p>";
        result += "</div>";
        
        document.getElementById('suhuResult').innerHTML = result;
    }

    // 5. Kasir Sederhana
    function kasir() {
        const namaBarang = document.getElementById('namaBarang').value;
        const hargaBarang = parseFloat(document.getElementById('hargaBarang').value);
        const jumlahBarang = parseInt(document.getElementById('jumlahBarang').value);
        
        if (!namaBarang || isNaN(hargaBarang) || isNaN(jumlahBarang)) {
            document.getElementById('kasirResult').innerHTML = 
                "<div class='result'>Masukkan data yang valid!</div>";
            return;
        }
        
        const total = hargaBarang * jumlahBarang;
        
        let result = "<div class='result'>";
        result += "<h3>Struk Pembayaran:</h3>";
        result += "<p><strong>Barang:</strong> " + namaBarang + "</p>";
        result += "<p><strong>Harga per unit:</strong> Rp " + hargaBarang.toLocaleString('id-ID') + "</p>";
        result += "<p><strong>Jumlah:</strong> " + jumlahBarang + "</p>";
        result += "<p><strong><u>Total Pembayaran:</u></strong> Rp " + total.toLocaleString('id-ID') + "</p>";
        result += "</div>";
        
        document.getElementById('kasirResult').innerHTML = result;
    }

    // 6. Luas Persegi Panjang
    function luasPersegi() {
        const panjang = parseFloat(document.getElementById('panjang').value);
        const lebar = parseFloat(document.getElementById('lebar').value);
        
        if (isNaN(panjang) || isNaN(lebar)) {
            document.getElementById('luasResult').innerHTML = 
                "<div class='result'>Masukkan panjang dan lebar yang valid!</div>";
            return;
        }
        
        const luas = panjang * lebar;
        
        let result = "<div class='result'>";
        result += "<h3>Hasil Perhitungan Luas:</h3>";
        result += "<p><strong>Panjang:</strong> " + panjang + "</p>";
        result += "<p><strong>Lebar:</strong> " + lebar + "</p>";
        result += "<p><strong>Luas:</strong> " + luas + " satuan²</p>";
        result += "<p><em>Rumus: Luas = panjang × lebar</em></p>";
        result += "</div>";
        
        document.getElementById('luasResult').innerHTML = result;
    }
</script>

</body>
</html>
