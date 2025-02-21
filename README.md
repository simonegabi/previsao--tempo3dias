# previsao--tempo3dias
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Previsão do Tempo - Próximos Dias</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #56ccf2, #2f80ed);
            text-align: center;
            color: white;
            padding: 50px;
        }
        .container {
            background: #fff;
            color: #333;
            border-radius: 15px;
            padding: 30px;
            width: 400px;
            margin: auto;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        h1 {
            color: #2f80ed;
        }

        select, button {
            width: 70%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
            margin: 10px 0;
        }

        button {
            background-color: #2f80ed;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 10px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #1c5bb5;
        }

        #resultado {
            margin-top: 20px;
            font-size: 18px;
        }

        .icone {
            font-size: 40px;
            margin: 5px 0;
        }

        .dia {
            border: 1px solid #ccc;
            border-radius: 10px;
            margin: 10px 0;
            padding: 10px;
            background: #f0f0f0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Previsão do Tempo - 3 Dias</h1>
        <select id="cidade">
            <option value="São Paulo">São Paulo</option>
            <option value="Rio de Janeiro">Rio de Janeiro</option>
            <option value="Belo Horizonte">Belo Horizonte</option>
            <option value="Curitiba">Curitiba</option>
            <option value="Salvador">Salvador</option>
        </select>
        <button onclick="mostrarPrevisao()">Ver Previsão</button>
        <div id="resultado"></div>
    </div>
    <script>
        function mostrarPrevisao() {
            const cidade = document.getElementById('cidade').value;
            const resultado = document.getElementById('resultado');

            const previsoes = {
                "São Paulo": [
                    { dia: "Hoje", temp: 25, clima: "Ensolarado", icone: "☀" },
                    { dia: "Amanhã", temp: 27, clima: "Nublado", icone: "☁" },
                    { dia: "Depois de Amanhã", temp: 26, clima: "Chuvoso", icone: "🌧" }
                ],
                "Rio de Janeiro": [
                    { dia: "Hoje", temp: 30, clima: "Parcialmente Nublado", icone: "⛅" },
                    { dia: "Amanhã", temp: 31, clima: "Ensolarado", icone: "☀" },
                    { dia: "Depois de Amanhã", temp: 29, clima: "Chuvoso", icone: "🌧" }
                ],
                "Belo Horizonte": [
                    { dia: "Hoje", temp: 28, clima: "Nublado", icone: "☁" },
                    { dia: "Amanhã", temp: 29, clima: "Sol com Nuvens", icone: "🌤" },
                    { dia: "Depois de Amanhã", temp: 27, clima: "Ensolarado", icone: "☀" }
                ],
                "Curitiba": [
                    { dia: "Hoje", temp: 18, clima: "Chuvoso", icone: "🌧" },
                    { dia: "Amanhã", temp: 20, clima: "Nublado", icone: "☁" },
                    { dia: "Depois de Amanhã", temp: 19, clima: "Sol com Nuvens", icone: "🌤" }
                ],
                "Salvador": [
                    { dia: "Hoje", temp: 29, clima: "Sol com Nuvens", icone: "🌤" },
                    { dia: "Amanhã", temp: 30, clima: "Ensolarado", icone: "☀" },
                    { dia: "Depois de Amanhã", temp: 28, clima: "Parcialmente Nublado", icone: "⛅" }
                ]
            };

            const cidadeSelecionada = previsoes[cidade];
            if (cidadeSelecionada) {
                resultado.innerHTML = `<h2>${cidade}</h2>` + cidadeSelecionada.map(dia => `
                    <div class="dia">
                        <h3>${dia.dia}</h3>
                        <div class="icone">${dia.icone}</div>
                        <p>Temperatura: ${dia.temp}°C</p>
                        <p>Clima: ${dia.clima}</p>
                    </div>
                `).join('');
            } else {
                resultado.innerHTML = `<p>Selecione uma cidade válida.</p>`;
            }
        }
    </script>
</body>
</html>
