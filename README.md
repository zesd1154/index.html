<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>로그인 창</title>

    <!-- google font -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR&display=swap" rel="stylesheet">

    <style>
        /* reset style */
        * {
            box-sizing: border-box;
            font-family: 'Noto Sans KR', sans-serif;
        }
        html, body {
            margin:0;
            padding:0;
        }

        /* 화면 커버 디자인 */
        .login-cover {
            position: fixed;

            left:0;
            right:0;
            top:0;
            bottom:0;

            background:rgba(0, 0, 0, 0.3);
        }

        /* 로그인 영역 디자인 */
        .login-cover > .login-wrapper {
            background:#513e30;
            color: #c9b584;

            position:absolute;

            left:50%;
            top:50%;
            transform:translate(-50%, -50%);

            font-size: 30px;
            padding:1em;
            
            box-shadow: 0.35em 0.5em 0 0 black;

            width:15em;
        }

        /* 로그인 영역 내 행 디자인 */
        .login-cover > .login-wrapper > .row {
            margin:1em 0;
            position:relative;
        }
        .login-cover > .login-wrapper > .row.header {
            font-size: 2em;
            margin:0.5em 0;
            text-align: center;
            letter-spacing: 0.25em;
            color: #fae37d;
        }

        /* 입력창 및 버튼 디자인 */
        .login-cover > .login-wrapper input ,
        .login-cover > .login-wrapper button[type=submit] {
            width:100%;

            font:inherit;
            background:inherit;
            color:inherit;
            border:none; 
            /* border:0.1em solid #c9b584; */
            
            outline:none;

            padding:0.5em 0.25em;
        }

        .login-cover > .login-wrapper input {

        }

        .login-cover > .login-wrapper button[type=submit] {
            border:0.1em solid #c9b584;
            letter-spacing: 0.1em;
            cursor:pointer;
        }

        /* 입력창 위에 표시될 라벨 디자인 */
        .login-cover > .login-wrapper label {
            position:absolute;
            left:0.25em;
            top:0.5em;

            font:inherit;

            z-index: -1;
        }

        /* 입력창 하단 하이라이트 선 디자인 */
        .login-cover > .login-wrapper .highlight {
            position:absolute;
            left:0;
            bottom:0;
            right:0;
            height:0.1em;
            background: #c9b584;
        }

        /* 부드러운 이동을 위한 transition 처리 */
        .login-cover > .login-wrapper label,
        .login-cover > .login-wrapper .highlight {
            transition: all 0.2s ease-out;
        }

        /* 입력창에 값이 입력되거나 커서가 위치할 경우 이동 처리 */
        .login-cover > .login-wrapper input:focus + label,
        .login-cover > .login-wrapper input:valid + label {
            left:0.25em;
            top:-0.75em;
            font-size: 0.75em;
            background: #513e30;
            z-index: 1;

            color:#fae37d;
        }
        .login-cover > .login-wrapper input:focus ~ .highlight,
        .login-cover > .login-wrapper input:valid ~ .highlight {
            /* background:#fae37d;*/
        }

        /* 버튼 배경 그라데이션 추가 */
        .login-cover > .login-wrapper button[type=submit] {
            background: rgb(255,255,255);
            background: linear-gradient(90deg, rgba(255,255,255,0) 0%, rgba(201,181,132,0) 25%, rgba(226,204,129,0.7511379551820728) 40%, rgba(250,227,125,1) 50%, rgba(226,204,129,0.75) 60%, rgba(255, 255, 255, 0) 75%, rgba(255,255,255,0) 100%);
            background-size: 500%;
            background-position: 0 0;

            transition: background 0.5s ease-out;
        }
        .login-cover > .login-wrapper button[type=submit]:hover {
            border-color: #fae37d;
            color:#fae37d;

            background-position: 100% 0;
        }

        /* 하이라이트 선을 부드럽게 표시되도록 애니메이션 처리 */
        .login-cover > .login-wrapper .highlight::after {
            content :"";
            position:absolute;
            left:0;
            bottom:0;
            height:0.1em;
            right:100%;
            
            background: #fae37d;

            transition:right 0.2s ease-out;
        }
        .login-cover > .login-wrapper input:focus ~ .highlight::after,
        .login-cover > .login-wrapper input:valid ~ .highlight::after {
            right:0;
        }
    </style>
</head>
<body>
    
    <!-- 화면 커버 -->
    <div class="login-cover">

        <!-- 로그인 영역 -->
        <div class="login-wrapper">
            
            <div class="row header">
                LOGIN
            </div>

            <div class="row">
                <input type="text" name="id" required autocomplete="off">
                <label>ID</label>
                <div class="highlight"></div>
            </div>

            <div class="row">
                <input type="password" name="pw" required>
                <label>Password</label>
                <div class="highlight"></div>
            </div>

            <div class="row">
                <button type="submit">login</button>
            </div>

        </div>

    </div>

</body>
</html>
