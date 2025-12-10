<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Calculadora de Horas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #111;
            color: #fff;
            padding: 20px;
        }
        .card {
            background: #1b1b1b;
            padding: 20px;
            border-radius: 12px;
            max-width: 500px;
            margin: auto;
        }
        input {
            width: 100%;
            padding: 10px;
            margin: 6px 0;
            border-radius: 6px;
            border: none;
        }
        button {
            width: 100%;
            padding: 12px;
            margin-top: 10px;
            background: #007bff;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background: #005fcc;
        }
        .resultado {
            margin-top: 15px;
            font-size: 18px;
            word-break: break-word;
        }
    </style>
</head>
<body>
    <div class="card">
        <h2>Calculadora de Horas</h2>

        <label>Somar Horas (formato HH:MM:SS, uma por linha)</label>
        <textarea id="lista" rows="6" style="width:100%; border-radius:8px; padding:10px;"></textarea>
        <button onclick="somarHoras()">Somar Horas</button>

        <hr />

        <label>Subtrair duas horas (HH:MM:SS)</label>
        <input id="hora1" placeholder="Hora 1" />
        <input id="hora2" placeholder="Hora 2" />
        <button onclick="subtrairHoras()">Subtrair</button>

        <div class="resultado" id="resultado"></div>
    </div>

    <script>
        function paraSegundos(hms) {
            const [h, m, s] = hms.split(":").map(Number);
            return h * 3600 + m * 60 + s;
        }

        function formatar(seg) {
            const h = Math.floor(seg / 3600);
            const m = Math.floor((seg % 3600) / 60);
            const s = seg % 60;
            return `${String(h).padStart(2,"0")}:${String(m).padStart(2,"0")}:${String(s).padStart(2,"0")}`;
        }

        function somarHoras() {
            const linhas = document.getElementById("lista").value.split(/\n+/);
            let total = 0;
            linhas.forEach(l => {
                if (l.trim()) total += paraSegundos(l.trim());
            });
            document.getElementById("resultado").innerText =
                "Total: " + formatar(total);
        }

        function subtrairHoras() {
            const h1 = document.getElementById("hora1").value;
            const h2 = document.getElementById("hora2").value;

            if (!h1 || !h2) return alert("Preencha as duas horas!");

            const dif = paraSegundos(h1) - paraSegundos(h2);
            document.getElementById("resultado").innerText =
                "Resultado: " + formatar(Math.abs(dif));
        }
    </script>
</body>
</html>
