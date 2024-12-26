<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>课堂时段准确率</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        th {
            background-color: #f4f4f4;
        }
    </style>
</head>
<body>
    <h2>时间段重叠分析工具</h2>
    <table>
        <thead>
            <tr>
                <th>问题</th>
                <th>起止时间</th>
                <th>人工时间</th>
                <th>重叠时间(s)</th>
                <th>准确率</th>
                <th>召回率</th>
                <th>F1分数</th>
            </tr>
        </thead>
        <tbody id="results"></tbody>
    </table>
    <h3 id="summary"></h3>

    <script>
        const data = [
            { "问题": "那像这样的复姓，你还知道哪些？", "起止时间": "00:01:14 - 00:01:17", "人工时间": "00:01:09 - 00:01:14" },
            { "问题": "司马想到了谁？", "起止时间": "00:01:33 - 00:01:36", "人工时间": "00:01:32 - 00:01:36" }
        ];

        function timeToSeconds(time) {
            const [hours, minutes, seconds] = time.split(':').map(Number);
            return hours * 3600 + minutes * 60 + seconds;
        }

        function calculateOverlap(modelTime, humanTime) {
            const [mStart, mEnd] = modelTime.split(' - ').map(timeToSeconds);
            const [hStart, hEnd] = humanTime.split(' - ').map(timeToSeconds);
            const overlap = Math.max(0, Math.min(mEnd, hEnd) - Math.max(mStart, hStart));
            return {
                overlap,
                modelDuration: mEnd - mStart,
                humanDuration: hEnd - hStart
            };
        }

        function calculateMetrics(overlap, modelDuration, humanDuration) {
            const accuracy = modelDuration ? (overlap / modelDuration).toFixed(2) : 0;
            const recall = humanDuration ? (overlap / humanDuration).toFixed(2) : 0;
            const f1 = (accuracy && recall) ? (2 * accuracy * recall / (Number(accuracy) + Number(recall))).toFixed(2) : 0;
            return { accuracy, recall, f1 };
        }

        let totalAccuracy = 0, totalRecall = 0, totalF1 = 0, count = 0;
        data.forEach(item => {
            if (item.起止时间 && item.人工时间) {
                const { overlap, modelDuration, humanDuration } = calculateOverlap(item.起止时间, item.人工时间);
                const { accuracy, recall, f1 } = calculateMetrics(overlap, modelDuration, humanDuration);
                totalAccuracy += Number(accuracy);
                totalRecall += Number(recall);
                totalF1 += Number(f1);
                count++;
                document.getElementById('results').innerHTML += `
                    <tr>
                        <td>${item.问题}</td>
                        <td>${item.起止时间}</td>
                        <td>${item.人工时间}</td>
                        <td>${overlap}</td>
                        <td>${accuracy}</td>
                        <td>${recall}</td>
                        <td>${f1}</td>
                    </tr>
                `;
            }
        });

        document.getElementById('summary').innerText = `平均准确率: ${(totalAccuracy / count).toFixed(2)}, 平均召回率: ${(totalRecall / count).toFixed(2)}, 平均F1分数: ${(totalF1 / count).toFixed(2)}`;
    </script>
</body>
</html>
