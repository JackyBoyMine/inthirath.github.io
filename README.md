<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>terminal — brian</title>
  <style>
    :root {
      --bg: #000;
      --fg: #fff;
      --muted: #888;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      cursor: none; /* hide default cursor */
    }

    body {
      background: var(--bg);
      color: var(--fg);
      font-family: "Courier New", monospace;
      padding: 40px;
      line-height: 1.6;
      font-size: 16px;
    }

    .grid {
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(var(--muted) 1px, transparent 1px),
        linear-gradient(90deg, var(--muted) 1px, transparent 1px);
      background-size: 40px 40px;
      opacity: 0.05;
      pointer-events: none;
      z-index: -1;
    }

    .prompt {
      color: var(--muted);
    }

    a {
      color: var(--fg);
      text-decoration: none;
      border-bottom: 1px dashed var(--fg);
    }

    /* mouse trail dots */
    .dot {
      position: fixed;
      width: 6px;
      height: 6px;
      background: var(--fg);
      border-radius: 50%;
      pointer-events: none;
      opacity: 0.9;
      transform: translate(-50%, -50%);
      animation: fade 0.4s linear forwards;
    }

    @keyframes fade {
      from { opacity: 0.9; }
      to { opacity: 0; transform: translate(-50%, -50%) scale(0.4); }
    }
  </style>
</head>
<body>

<div class="grid"></div>

<div>
  <span class="prompt">brian@portfolio:~$</span> whoami  
  <br>Brian — CS @ GSU, building things and learning nonstop.
  <br><br>

  <span class="prompt">brian@portfolio:~$</span> ls resume  
  <br><a href="resume.pdf" target="_blank">resume.pdf</a>
  <br><br>

  <span class="prompt">brian@portfolio:~$</span> ls projects  
  <br><a href="#">project_1</a>
  <br><a href="#">project_2</a>
  <br><a href="#">project_3</a>
  <br><br>

  <span class="prompt">brian@portfolio:~$</span> ls contact  
  <br><a href="#">github</a>
  <br><a href="#">linkedin</a>
  <br><a href="#">email</a>
  <br><br>

  <span class="prompt">brian@portfolio:~$</span> _
</div>

<script>
  document.addEventListener("mousemove", e => {
    const dot = document.createElement("div");
    dot.className = "dot";
    dot.style.left = e.pageX + "px";
    dot.style.top = e.pageY + "px";
    document.body.appendChild(dot);
    setTimeout(() => dot.remove(), 400);
  });
</script>

</body>
</html>
