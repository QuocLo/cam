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
    document.addEventListener('DOMContentLoaded', function () {
        const textConfig = {
            // ... (Các text messages của bạn)
        };

        const questions = [
            {
                title: textConfig.text1,
                text: textConfig.text2,
                imageUrl: "https://i.pinimg.com/736x/ac/bd/d1/acbdd141066e674324f1115d135764c7.jpg",
                imageWidth: 300,
                imageHeight: 300,
                background: '#fff url("img/iput-bg.jpg")',
                imageAlt: "https://i.pinimg.com/736x/ac/bd/d1/acbdd141066e674324f1115d135764c7.jpg",
            },
            {
                title: textConfig.text3,
                text: textConfig.text4,
                imageUrl: "https://gcs.tripi.vn/public-tripi/tripi-feed/img/474093rCo/meme-cam-trai-tim_035159914.jpg",
                imageWidth: 300,
                imageHeight: 300,
                background: 'https://staticg.sportskeeda.com/editor/2023/12/5a745-17014669361362-1920.jpg?w=840',
                imageAlt: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsXUf6hfdauGohoRHuw0jphqfGQF9LveI5k09-MGl1VQ&s",
            },
            // ... (Thêm câu hỏi khác nếu cần)
        ];

        const userAnswers = [];

        function displayQuestion(index) {
            const question = questions[index];

            Swal.fire({
                title: question.title,
                text: question.text,
                imageUrl: question.imageUrl,
                imageWidth: question.imageWidth,
                imageHeight: question.imageHeight,
                background: question.background,
                imageAlt: question.imageAlt,
            }).then(function () {
                const userAnswer = prompt("Nhập câu trả lời của bạn:");
                userAnswers.push({ questionIndex: index, answer: userAnswer });

                if (index + 1 < questions.length) {
                    displayQuestion(index + 1);
                } else {
                    showFinalResult();
                }
            });
        }

        function showFinalResult() {
            // Xử lý và hiển thị kết quả cuối cùng dựa trên userAnswers
            console.log(userAnswers);
        }

        // Kiểm tra xem người dùng đã trả lời câu hỏi nào trước đó hay chưa
        const savedUserAnswers = JSON.parse(localStorage.getItem('userAnswers'));
        if (savedUserAnswers && Array.isArray(savedUserAnswers) && savedUserAnswers.length > 0) {
            if (confirm("Bạn muốn tiếp tục câu chuyện từ đâu bạn đã dừng lại không?")) {
                userAnswers.push(...savedUserAnswers);
                displayQuestion(userAnswers[userAnswers.length - 1].questionIndex + 1);
            } else {
                localStorage.removeItem('userAnswers');
                displayQuestion(0);
            }
        } else {
            displayQuestion(0);
        }

        window.addEventListener('beforeunload', function () {
            // Lưu trạng thái người dùng trước khi họ thoát trang
            localStorage.setItem('userAnswers', JSON.stringify(userAnswers));
        });
    });
</script>
</body>
</html>
