<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Avaliação Dinâmica</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f4f4f9;
            color: #333;
        }
        .container {
            max-width: 600px;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            margin: 0 auto;
        }
        h2, h3 { text-align: center; color: #444; }
        .form-group { margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input[type="text"], input[type="number"], select, textarea {
            width: 100%;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 10px;
        }
        button:hover { background-color: #0056b3; }
        .secondary-btn { background-color: #28a745; }
        .secondary-btn:hover { background-color: #218838; }
        .hidden { display: none; }
        .questao { background: #f9f9f9; padding: 15px; margin-bottom: 15px; border-left: 4px solid #007bff; border-radius: 4px; }
        .opcoes label { font-weight: normal; margin-bottom: 2px; }
    </style>
</head>
<body>

<div class="container">
    <div id="tela-inicial">
        <h2>Sistema de Provas</h2>
        <button onclick="acessarPainelProfessor()">Painel do Professor</button>
        <button class="secondary-btn" onclick="acessarPainelAluno()">Realizar Prova (Aluno)</button>
    </div>

    <div id="painel-professor" class="hidden">
        <h2>Configuração da Avaliação</h2>
        <div class="form-group">
            <label>Nome do Professor:</label>
            <input type="text" id="prof-nome">
        </div>
        <div class="form-group">
            <label>Escola:</label>
            <input type="text" id="prof-escola">
        </div>
        <div class="form-group">
            <label>Assunto da Avaliação:</label>
            <input type="text" id="prof-assunto">
        </div>
        <div class="form-group">
            <label>Conteúdo da Prova (Cole o texto base aqui):</label>
            <textarea id="prof-conteudo" rows="5"></textarea>
        </div>
        <div class="form-group">
            <label>Quantidade de Perguntas:</label>
            <input type="number" id="prof-qtd-perguntas" min="1" value="1">
        </div>
        <div class="form-group">
            <label>Tipo de Prova:</label>
            <select id="prof-tipo-prova">
                <option value="objetiva">Objetiva (A, B, C, D, E)</option>
                <option value="descritiva">Descritiva (Dissertativa)</option>
            </select>
        </div>
        <button onclick="salvarConfiguracao()">Salvar e Criar Prova</button>
        <button style="background-color: #6c757d;" onclick="voltarInicio()">Voltar</button>
    </div>

    <div id
