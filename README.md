# html-lista-certo


<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <title>Sistema Escolar</title>
    <style>
        /* Fundo e fonte */
        body {
            background: linear-gradient(135deg, #dbeafe, #f0f9ff);
            font-family: Arial, Helvetica, sans-serif;
            margin: 0;
            padding: 0;
        }

        /* Título da página */
        .titulo {
            font-size: 26px;
            color: #1e3a8a;
            margin-top: 40px;
            text-align: center;
        }

        .titulo p {
            color: #475569;
            font-size: 16px;
        }

        /* Formulário */
        .formulario {
            background-color: white;
            width: 650px;
            max-width: 90%;
            padding: 30px;
            border-radius: 12px;
            border: 1px solid #cbd5e1;
            margin: 30px auto;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
        }

        label {
            font-weight: bold;
            color: #334155;
            display: block;
            text-align: left;
            margin-top: 15px;
        }

        input, select {
            width: 95%;
            padding: 10px;
            margin-top: 5px;
            border-radius: 6px;
            border: 1px solid #cbd5e1;
            font-size: 14px;
        }

        input:focus, select:focus {
            outline: none;
            border: 1px solid #2563eb;
            box-shadow: 0 0 5px rgba(37, 99, 235, 0.4);
        }

        /* Botão */
        .cadastrar {
            cursor: pointer;
            display: block;
            margin: 25px auto 0 auto;
            padding: 12px 25px;
            font-size: 16px;
            background-color: #2563eb;
            color: white;
            border: none;
            border-radius: 8px;
            transition: 0.3s;
        }

        .cadastrar:hover {
            background-color: #1e40af;
            transform: scale(1.05);
        }

        /* Resultado */
        #resultado {
            background-color: white;
            width: 650px;
            max-width: 90%;
            padding: 25px;
            border-radius: 12px;
            border: 1px solid #cbd5e1;
            margin: 20px auto;
            display: none;
            text-align: left;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
        }

        #resultado h2 {
            color: #1e3a8a;
            text-align: center;
        }
    </style>
</head>

<body>

    <div class="titulo">
        <h1>EEB Dom Jaime de Barros Câmara</h1>
        <p>Preencha o formulário abaixo para cadastrar um novo aluno</p>
    </div>

    <div class="formulario">
        <form id="formAluno" onsubmit="MostrarDados(event)">

            <label for="nome">Nome do Aluno:</label>
            <input type="text" id="nome" required>

            <label for="datanasc">Data de Nascimento:</label>
            <input type="date" id="datanasc" required>

            <label for="cpf">CPF do Aluno:</label>
            <input type="text" id="cpf" required>

            <label for="cpfMae">CPF da Mãe:</label>
            <input type="text" id="cpfMae" required>

            <label for="cpfPai">CPF do Pai:</label>
            <input type="text" id="cpfPai" required>

            <label for="email">Email:</label>
            <input type="email" id="email" required>

            <label for="turno">Turno:</label>
            <select id="turno" required>
                <option value="">Selecione</option>
                <option value="Manhã">Manhã</option>
                <option value="Tarde">Tarde</option>
                <option value="Noite">Noite</option>
            </select>

            <label for="anoEscolar">Ano Escolar:</label>
            <select id="anoEscolar" required>
                <option value="">Selecione</option>
                <option value="1º Ano">1º Ano</option>
                <option value="2º Ano">2º Ano</option>
                <option value="3º Ano">3º Ano</option>
                <option value="4º Ano">4º Ano</option>
                <option value="5º Ano">5º Ano</option>
                <option value="6º Ano">6º Ano</option>
                <option value="7º Ano">7º Ano</option>
                <option value="8º Ano">8º Ano</option>
                <option value="9º Ano">9º Ano</option>
            </select>

            <button type="submit" class="cadastrar">Cadastrar</button>
        </form>
    </div>

    <div id="resultado"></div>

    <script>
        function MostrarDados(event) {
            event.preventDefault(); // Evita recarregar a página

            let nome = document.getElementById("nome").value;
            let dataNasc = document.getElementById("datanasc").value;
            let cpf = document.getElementById("cpf").value;
            let cpfMae = document.getElementById("cpfMae").value;
            let cpfPai = document.getElementById("cpfPai").value;
            let email = document.getElementById("email").value;
            let turno = document.getElementById("turno").value;
            let anoEscolar = document.getElementById("anoEscolar").value;

            let resultado = document.getElementById("resultado");

            resultado.innerHTML =
                `<h2>Dados do Aluno</h2>
                <p><strong>Nome:</strong> ${nome}</p>
                <p><strong>Data de Nascimento:</strong> ${dataNasc}</p>
                <p><strong>CPF do Aluno:</strong> ${cpf}</p>
                <p><strong>CPF da Mãe:</strong> ${cpfMae}</p>
                <p><strong>CPF do Pai:</strong> ${cpfPai}</p>
                <p><strong>Email:</strong> ${email}</p>
                <p><strong>Turno:</strong> ${turno}</p>
                <p><strong>Ano Escolar:</strong> ${anoEscolar}</p>`;

            resultado.style.display = "block";

            // Limpar o formulário
            document.getElementById("formAluno").reset();
        }
    </script>

</body>

</html>
