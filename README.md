<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>長野市 眼科ガイド</title>
    <style>
        :root {
            --primary-color: #2c7be5;
            --bg-color: #f8f9fa;
        }
        body {
            font-family: "Helvetica Neue", Arial, "Hiragino Kaku Gothic ProN", "Hiragino Sans", sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            background-color: var(--bg-color);
            color: #333;
        }
        .container {
            max-width: 1000px;
            margin: auto;
            background: white;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        h1 {
            color: var(--primary-color);
            border-bottom: 3px solid var(--primary-color);
            padding-bottom: 10px;
            text-align: center;
        }
        .search-box {
            margin-bottom: 20px;
            text-align: right;
        }
        input[type="text"] {
            padding: 10px;
            width: 250px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }
        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #eee;
        }
        th {
            background-color: #f2f2f2;
            color: #555;
            font-weight: bold;
        }
        tr:hover {
            background-color: #fdfdfd;
        }
        .status-tag {
            display: inline-block;
            padding: 2px 8px;
            border-radius: 4px;
            font-size: 0.85em;
            font-weight: bold;
        }
        .has-lasik { background-color: #e3f2fd; color: #1976d2; }
        .no-lasik { background-color: #f5f5f5; color: #757575; }
        
        @media (max-width: 768px) {
            table, thead, tbody, th, td, tr { display: block; }
            th { display: none; }
            tr { margin-bottom: 15px; border: 1px solid #ddd; padding: 10px; border-radius: 8px; }
            td { border: none; padding-left: 50%; position: relative; }
            td:before {
                content: attr(data-label);
                position: absolute; left: 10px; font-weight: bold; color: var(--primary-color);
            }
        }
    </style>
</head>
<body>

<div class="container">
    <h1>長野市 眼科情報ガイド</h1>
    
    <div class="search-box">
        <input type="text" id="searchInput" onkeyup="filterTable()" placeholder="医院名やキーワードで検索...">
    </div>

    <table id="gankaTable">
        <thead>
            <tr>
                <th>医院名</th>
                <th>住所</th>
                <th>営業時間</th>
                <th>休業日</th>
                <th>電話番号</th>
                <th>レーシック/ICL</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td data-label="医院名">博愛こばやし眼科</td>
                <td data-label="住所">長野市稲里町下氷鉋488</td>
                <td data-label="営業時間">9:00-12:00 / 14:00-17:00</td>
                <td data-label="休業日">日・祝・水午後</td>
                <td data-label="電話番号">026-285-9939</td>
                <td data-label="レーシック/ICL"><span class="status-tag has-lasik">ICL対応</span></td>
            </tr>
            <tr>
                <td data-label="医院名">石田眼科長野クリニック</td>
                <td data-label="住所">長野市大字鶴賀緑町1102</td>
                <td data-label="営業時間">9:00-12:00 / 15:00-18:00</td>
                <td data-label="休業日">日・祝・木土午後</td>
                <td data-label="電話番号">026-226-7620</td>
                <td data-label="レーシック/ICL"><span class="status-tag has-lasik">手術実績豊富</span></td>
            </tr>
            <tr>
                <td data-label="医院名">おおくぼ眼科</td>
                <td data-label="住所">長野市南千歳1-1-1 ながの東急6F</td>
                <td data-label="営業時間">10:00-13:00 / 14:30-18:30</td>
                <td data-label="休業日">木曜・休館日</td>
                <td data-label="電話番号">026-269-0009</td>
                <td data-label="レーシック/ICL"><span class="status-tag no-lasik">一般・コンタクト</span></td>
            </tr>
            <tr>
                <td data-label="医院名">三輪眼科</td>
                <td data-label="住所">長野市三輪3-19-17</td>
                <td data-label="営業時間">9:00-12:00 / 15:00-18:00</td>
                <td data-label="休業日">日・祝・水木午後</td>
                <td data-label="電話番号">026-259-5959</td>
                <td data-label="レーシック/ICL"><span class="status-tag no-lasik">一般・小児</span></td>
            </tr>
        </tbody>
    </table>
</div>

<script>
function filterTable() {
    let input = document.getElementById("searchInput");
    let filter = input.value.toLowerCase();
    let table = document.getElementById("gankaTable");
    let tr = table.getElementsByTagName("tr");

    for (let i = 1; i < tr.length; i++) {
        let textContent = tr[i].textContent.toLowerCase();
        tr[i].style.display = textContent.includes(filter) ? "" : "none";
    }
}
</script>

</body>
</html>
