---
title: "PKU Video Download"
layout: homepageDefault
permalink: /pkuVideo/
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>课堂实录下载</title>
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
