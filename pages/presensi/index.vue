<script setup>
definePageMeta({
    layout: 'admin',
    middleware: 'auth'
})

</script>

<template>
    <!DOCTYPE html>
        <div class="container">
            <h1>Presensi Kelas</h1>
            <form id="attendance-form">
                <label for="student-name">Nama Siswa:</label>
                <input type="text" id="student-name" name="student-name" required>

                <label for="attendance-status">Status Kehadiran:</label>
                <select id="attendance-status" name="attendance-status" required>
                    <option value="hadir">Hadir</option>
                    <option value="tidak hadir">Tidak Hadir</option>
                    <option value="izin">Izin</option>
                </select>

                <button type="submit">Kirim</button>
            </form>

            <h2>Daftar Kehadiran</h2>
            <table id="attendance-table">
                <thead>
                    <tr>
                        <th>Nama Siswa</th>
                        <th>Status Kehadiran</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- Data presensi akan ditambahkan di sini -->
                </tbody>
            </table>
        </div>

</template>

<style scoped>
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 20px;
}

.container {
    max-width: 600px;
    margin: auto;
    background: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h1, h2 {
    text-align: center;
}

form {
    display: flex;
    flex-direction: column;
}

label {
    margin: 10px 0 5px;
}

input, select {
    padding: 10px;
    margin-bottom: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    padding: 10px;
    background-color: #28a745;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #218838;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

th, td {
    padding: 10px;
    text-align: left;
    border-bottom: 1px solid #ddd;
}

th {
    background-color: #f2f2f2;
}
</style>