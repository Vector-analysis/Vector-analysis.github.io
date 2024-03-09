---
title: "PKU Video Download"
layout: plain
permalink: /pkuVideo/
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>课堂实录下载</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            margin: 0;
            padding: 0;
        }

        h1 {
            text-align: center;
            color: #333;
        }

        .container {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .instruction {
            margin-bottom: 20px;
        }

        .input-wrapper {
            margin-bottom: 30px;
        }

        input[type="text"] {
            width: calc(100% - 80px);
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
            outline: none;
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #0056b3;
        }

        .donation {
            text-align: center;
            margin-top: 40px;
            font-size: 10px;
            color: #666;
        }

        .monero-address {
            display: inline;
            margin: 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>课堂实录下载</h1>
        <div class="instruction">
            请在观看页面，点击“复制下载地址”后，粘贴到下方输入框中<br/>
			如果没有找到“复制下载地址”按钮，请向下滚动页面
        </div>
        <div class="input-wrapper">
            <input type="text" id="textInput" placeholder="下载地址">
            <button onclick="checkPattern()">下载</button>
        </div>
    </div>

    <div class="donation">
        Donate with RVN: <span class="monero-address">r9JjJwqvBucg9j5bUBPmcNWVaQNuQJe6F8</span>
    </div>

    <script>
        function checkPattern() {
            var inputText = document.getElementById("textInput").value;
            var mp4Pattern = /http.+\.mp4\?.*/;
            var m3u8Pattern = /https:\/\/resourcese\.pku\.edu\.cn\/play\/0\/harpocrates\/\d*\/\d*\/\d*\/([a-zA-Z0-9]+)\/0\/playlist\.m3u8\?.*/;

            if (mp4Pattern.test(inputText)) {
                window.location.href = inputText;
            } else if (m3u8Pattern.test(inputText)) {
                var matches = inputText.match(m3u8Pattern);
                var hash = matches[1];
                window.location.href = 'https://course.pku.edu.cn/webapps/bb-streammedia-hqy-BBLEARN/downloadVideo.action?resourceId=' + hash;
            } else {
                alert("无法识别的下载地址.");
            }
        }
    </script>
</body>
</html>
