<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Love+Ya+Like+A+Sister&family=Lovers+Quarrel&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="style.css">
  <title>Valentine Project</title>
</head>
<body>
<div id="root"></div>

<script>
  const phrases = [
    "No 🙉",
    "Are you sure?",
    "Really Sure😢",
    "I'll be very sad😕",
    "You're the sunshine of my life 💐",
    "Your smile is my favorite 🥰",
    "You make my heart skip a beat 💓",
    "Pookie Please🥺",
    "Don't do this to me🫤",
    "I'm gonna cry..😭",
    "You are breaking my heart😭💔",
  ];

  let noCount = 0;
  let yesPressed = false;
  let yesButtonSize = 16;

  function handleYesClick() {
    yesPressed = true;
    render();
  }

  function handleNoClick() {
    noCount += 1;
    yesButtonSize += 20;
    render();
  }

  function getNoButtonText() {
    return phrases[Math.min(noCount, phrases.length - 1)];
  }

  function render() {
    const root = document.getElementById('root');

    if (yesPressed) {
      root.innerHTML = `
                    <img src="https://media.tenor.com/gUiu1zyxfzYAAAAi/bear-kiss-bear-kisses.gif" alt="bear-Kissing" />
                    <div class='text'>Yayyy !!!</div>
                `;
    } else {
      root.innerHTML = `
                    <img class='kiss' src="https://media1.tenor.com/m/al4a1pG1f8YAAAAC/jump-bear.gif" alt="bear with heart" />
                    <div class='text'>Will you be my valentine 🌹?</div>
                    <div class='both-Button'>
                        <button class='yesButton' style="font-size: ${yesButtonSize}px; background-color: rgb(248, 229, 89)" onclick="handleYesClick()">
                            Yes 🙈
                        </button>
                        <button class='NoButton' onclick="handleNoClick()">
                            ${getNoButtonText()}
                        </button>
                    </div>
                `;
    }
  }

  render();
</script>

</body>
</html>
