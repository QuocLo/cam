<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dành Cho Mỗi Cam Thôi</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/sweetalert2@11.0.20/dist/sweetalert2.min.css">
</head>
<body>

<script src="https://cdn.jsdelivr.net/npm/sweetalert2@11.0.20/dist/sweetalert2.min.js"></script>
<script>
    const textConfig = {
        text1: "He luu béeeee!",
        text2: "Anh có điều này muốn hỏi bée nhớ phải trả lời thật lòng nhaaa.",
        text3: "Bé yêu Anh có phải không nào ._.",
        text4: "Nếu bée ko trả lời mà thoát ra tức là muốn làm vại tương lơ của anh rùi đó nha :33",
        text5: "Cậu mơ à???",
        text6: "Yêu ơi là yêu <3",
        text7: "Lí do bé thích anh iiiii :333",
        text8: "Gửi cho Anhhh <3",
        text9: "Vì Anhhhh đẹp try vlllll",
        text10: "Anhh biết mà ^^ Yêu Bée 300.000",
        text11: "Còn giờ thì chờ gì nữa mà ko inbox cho anh đi nàooo",
        text12: "Okii lunn <3",
    };

    document.addEventListener('DOMContentLoaded', function () {
        setTimeout(function () {
            firstQuestion();
        }, 600);

        function firstQuestion() {
            Swal.fire({
                title: textConfig.text1,
                text: textConfig.text2,
                imageUrl: "https://i.pinimg.com/736x/ac/bd/d1/acbdd141066e674324f1115d135764c7.jpg",
                imageWidth: 300,
                imageHeight: 300,
                background: '#fff url("img/iput-bg.jpg")',
                imageAlt: "https://i.pinimg.com/736x/ac/bd/d1/acbdd141066e674324f1115d135764c7.jpg",
            }).then(function () {
                secondQuestion();
            });
        }

        function secondQuestion() {
            Swal.fire({
                title: textConfig.text3,
                text: textConfig.text4,
                imageUrl: "https://gcs.tripi.vn/public-tripi/tripi-feed/img/474093rCo/meme-cam-trai-tim_035159914.jpg",
                imageWidth: 300,
                imageHeight: 300,
                background: 'https://staticg.sportskeeda.com/editor/2023/12/5a745-17014669361362-1920.jpg?w=840',
                imageAlt: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsXUf6hfdauGohoRHuw0jphqfGQF9LveI5k09-MGl1VQ&s",
            }).then(function () {
                thirdQuestion();
            });
        }

        function thirdQuestion() {
            Swal.fire({
                title: textConfig.text7,
                html: "<input type='text' class='form-control' id='txtReason'  placeholder='Whyyy'>",
                background: 'https://staticg.sportskeeda.com/editor/2023/12/5a745-17014669361362-1920.jpg?w=840',
                backdrop: ` `,
                showCancelButton: false,
                confirmButtonColor: "#3085d6",
                cancelButtonColor: "#d33",
                confirmButtonColor: "#fe8a71",
                cancelButtonColor: "#f6cd61",
                confirmButtonText: textConfig.text8,
            }).then(function (result) {
                if (result.value) {
                    Swal.fire({
                        title: textConfig.text10,
                        text: textConfig.text11,
                        confirmButtonColor: "#83d0c9",
                        onClose: function () {
                            window.location.href = "http://fb.com";
                        },
                    });
                }
            });

            const txtReason = document.getElementById('txtReason');
            txtReason.addEventListener('input', function () {
                const value = txtReason.value.trim();
                if (value.length > 0) {
                    txtReason.value = textConfig.text9;
                }
            });
        }
    });
</script>
</body>
</html>
