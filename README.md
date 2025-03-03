<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <title>Tab Navigation</title>
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        .tab-bar {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            display: flex;
            justify-content: space-around;
            background-color: white;
            border-top: 1px solid #ccc;
            padding: 5px 0;
        }

        .tab-item {
            text-align: center;
            flex: 1;
            font-size: 12px;
            cursor: pointer;
            padding: 5px 0;
            border-radius: 5px;
            -webkit-tap-highlight-color: transparent;
            color: gray;
            transition: color 0.5s ease-in-out;
        }

        .tab-item.active {
            color: red; /* Màu đỏ khi tab được chọn */
        }

        .tab-item img {
            width: 24px;
            height: 24px;
            display: block;
            margin: 0 auto 2px;
            transition: transform 0.2s ease-in-out;
        }

        .iframe-container {
            width: 100%;
            height: calc(100vh - 60px);
            border: none;
            transition: opacity 1s ease-in-out;
        }
    </style>
</head>
<body>

    <iframe id="iframe-content" class="iframe-container" src="https://turbolite.github.io/Main"></iframe>

    <div class="tab-bar">
        <div class="tab-item active" onclick="openTab('https://turbolite.github.io/Main', this)" data-tab="thietbi">
            <img src="https://i.imgur.com/YcNNVKr.png" alt="Thiết Bị">
            <span>Thiết Bị</span>
        </div>
 
        <div class="tab-item" onclick="openTab('https://turbolite.github.io/Game/', this)" data-tab="game">
            <img src="https://i.imgur.com/rvmhLgP.png" alt="Game">
            <span>Game</span>
        </div>
        <div class="tab-item" onclick="openTab('https://turbolite.github.io/Meow', this)" data-tab="quanly">
            <img src="https://i.imgur.com/mdFmmVr.png" alt="Khám Phá">
            <span>Khám Phá</span>
        </div>
        <div class="tab-item" onclick="openTab('https://www.youtube.com/@Tolamfixlag', this)" data-tab="home">
            <img src="https://i.imgur.com/gPPZf93.png" alt="Home">
            <span>Home</span>
        </div>
    </div>

    <script>
        function openTab(url, element) {
            document.getElementById('iframe-content').style.opacity = '0';

            setTimeout(() => {
                document.getElementById('iframe-content').src = url;
                document.getElementById('iframe-content').style.opacity = '1';
            }, 300);

            document.querySelectorAll('.tab-item').forEach(tab => {
                tab.classList.remove('active');

                // Đổi lại màu chữ thành xám
                tab.querySelector("span").style.color = "gray";

                if (tab.dataset.tab === "thietbi") {
                    tab.querySelector("img").src = "https://i.imgur.com/YcNNVKr.png";
                }
                if (tab.dataset.tab === "quanly") {
                    tab.querySelector("img").src = "https://i.imgur.com/mdFmmVr.png";
                }
                if (tab.dataset.tab === "game") {
                    tab.querySelector("img").src = "https://i.imgur.com/rvmhLgP.png";
                }
                if (tab.dataset.tab === "home") {
                    tab.querySelector("img").src = "https://i.imgur.com/gPPZf93.png";
                }
            });

            element.classList.add('active');

            // Đổi màu chữ của tab đang được chọn thành đỏ
            element.querySelector("span").style.color = "red";

            if (element.dataset.tab === "thietbi") {
                element.querySelector("img").src = "https://i.imgur.com/8AMk0TU.png";
            }
            if (element.dataset.tab === "quanly") {
                element.querySelector("img").src = "https://i.imgur.com/sPbMuuY.png";
            }
            if (element.dataset.tab === "game") {
                element.querySelector("img").src = "https://i.imgur.com/MD59IfV.png";
            }
            if (element.dataset.tab === "home") {
                element.querySelector("img").src = "https://i.imgur.com/WhQ50sV.png";
            }
        }
    </script>

</body>
</html>
