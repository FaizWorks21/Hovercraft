<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Hovercraft Animation</title>
<style>
    body {
        margin: 0;
        height: 100vh;
        background: linear-gradient(#0e0e0e, #1b1b1b);
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        font-family: monospace;
    }

    .container {
        position: relative;
        width: 100%;
        height: 300px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    /* ---- TYPEWRITER TEXT ---- */
    .typing-text {
        font-size: 2.3rem;
        font-weight: 700;
        color: #ff8b00;
        border-right: 4px solid #ff8b00;
        white-space: nowrap;
        overflow: hidden;
        width: 0;
        animation: typing 4s steps(40, end) forwards, blink .6s step-end infinite;
        margin-bottom: 40px;
    }

    @keyframes typing {
        from { width: 0 }
        to { width: 700px }
    }

    @keyframes blink {
        from, to { border-color: transparent }
        50% { border-color: #ff8b00 }
    }

    /* ---- WATER WAVES ---- */
    .water {
        position: absolute;
        bottom: 0;
        width: 160%;
        height: 100px;
        background: repeating-linear-gradient(
            -45deg,
            #4fa3ff,
            #4fa3ff 12px,
            #3686e0 12px,
            #3686e0 24px
        );
        animation: wave 6s linear infinite;
    }

    @keyframes wave {
        0% { transform: translateX(0); }
        100% { transform: translateX(-80px); }
    }

    /* ---- HOVERCRAFT ---- */
    .hovercraft {
        position: absolute;
        bottom: 55px;
        left: -200px;
        width: 160px;
        height: 70px;
        background: #ff7b00;
        border-radius: 50px;
        box-shadow: 0 8px 15px rgba(0,0,0,0.5);
        animation: move 10s linear infinite;
    }

    .hovercraft::before {
        content: "";
        position: absolute;
        inset: 8px;
        border-radius: 40px;
        border: 3px solid #ffffff;
    }

    .fan {
        position: absolute;
        right: -25px;
        top: 10px;
        width: 40px;
        height: 40px;
        border: 3px solid #000;
        border-radius: 50%;
        background: #e9e9e9;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .fan span {
        position: absolute;
        width: 3px;
        height: 80%;
        background: #000;
        animation: spin 0.15s linear infinite;
    }

    .fan span:nth-child(2) { transform: rotate(90deg); }

    @keyframes spin {
        0% { transform: rotate(0deg); }
        100% { transform: rotate(360deg); }
    }

    .skirt {
        position: absolute;
        bottom: -14px;
        left: 10px;
        right: 10px;
        height: 20px;
        background: #111;
        border-radius: 0 0 50px 50px;
        animation: hover 1.3s ease-in-out infinite;
    }

    @keyframes hover {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(3px); }
    }

    @keyframes move {
        0% { transform: translateX(0); }
        50% { transform: translateX(700px) translateY(-6px); }
        100% { transform: translateX(1400px); }
    }

</style>
</head>

<body>
<div class="container">
    <div class="typing-text">Goes where boats, drones & robots can’t</div>
    <div class="hovercraft">
        <div class="fan">
            <span></span>
            <span></span>
        </div>
        <div class="skirt"></div>
    </div>
    <div class="water"></div>
</div>
</body>
</html>
