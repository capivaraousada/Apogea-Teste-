<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Apogea Teste</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding-top: 50px;
    }
    #contador {
      font-size: 48px;
      color: #333;
    }
  </style>
</head>
<body>

  <h1>Apogea Teste</h1>
  <div id="contador">Carregando...</div>

  <script>
    // Defina a data do evento
    const dataEvento = new Date("2025-06-06T12:00:00").getTime();

    // Atualize o contador a cada segundo
    const intervalo = setInterval(function() {
      const agora = new Date().getTime();
      const tempoRestante = dataEvento - agora;

      if (tempoRestante <= 0) {
        clearInterval(intervalo);
        document.getElementById("contador").innerHTML = "O evento começou!";
      } else {
        const dias = Math.floor(tempoRestante / (1000 * 60 * 60 * 24));
        const horas = Math.floor((tempoRestante % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutos = Math.floor((tempoRestante % (1000 * 60 * 60)) / (1000 * 60));
        const segundos = Math.floor((tempoRestante % (1000 * 60)) / 1000);

        document.getElementById("contador").innerHTML =
          `${dias}d ${horas}h ${minutos}m ${segundos}s`;
      }
    }, 1000);
  </script>

</body>
</html>
