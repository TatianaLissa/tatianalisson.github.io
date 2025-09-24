<!-- index.html -->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Basson Aulas de Computação</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #fffacd; /* amarelo claro */
      display: flex;
      height: 100vh;
    }
    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      background: #fffacd;
      text-align: center;
      font-size: 2.5em;
      font-weight: bold;
      color: black;
      padding: 15px 0;
      box-shadow: 0 1px 3px rgba(0,0,0,0.1);
      z-index: 1000;
    }
    nav {
      background-color: #fffacd;
      padding-top: 90px; /* para descer abaixo do header */
      width: 180px;
      box-shadow: 1px 0 5px rgba(0,0,0,0.1);
      height: 100vh;
      box-sizing: border-box;
      position: fixed;
      top: 0;
      left: 0;
    }
    nav a {
      display: block;
      padding: 15px 20px;
      text-decoration: none;
      color: black;
      font-weight: bold;
      border-left: 5px solid transparent;
      transition: all 0.3s ease;
    }
    nav a:hover, nav a:focus {
      background-color: #f0e68c; /* tom amarelo mais escuro */
      border-left-color: black;
      outline: none;
    }
    main {
      margin-left: 180px;
      padding: 110px 20px 20px 20px;
      flex: 1;
    }
  </style>
</head>
<body>
  <header>Basson Aulas de Computação</header>
  <nav>
    <a href="cadastro.html">Cadastro</a>
    <a href="disciplinas.html">Disciplinas</a>
  </nav>
  <main>
    <h2>Bem-vindo à Basson Aulas de Computação</h2>
    <p>Use o menu à esquerda para navegar pelo site.</p>
  </main>
</body>
</html>
<!-- cadastro.html -->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Cadastro - Basson Aulas de Computação</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #fffacd;
      display: flex;
      height: 100vh;
    }
    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      background: #fffacd;
      text-align: center;
      font-size: 2.5em;
      font-weight: bold;
      color: black;
      padding: 15px 0;
      box-shadow: 0 1px 3px rgba(0,0,0,0.1);
      z-index: 1000;
    }
    nav {
      background-color: #fffacd;
      padding-top: 90px;
      width: 180px;
      box-shadow: 1px 0 5px rgba(0,0,0,0.1);
      height: 100vh;
      box-sizing: border-box;
      position: fixed;
      top: 0;
      left: 0;
    }
    nav a {
      display: block;
      padding: 15px 20px;
      text-decoration: none;
      color: black;
      font-weight: bold;
      border-left: 5px solid transparent;
      transition: all 0.3s ease;
    }
    nav a:hover, nav a:focus {
      background-color: #f0e68c;
      border-left-color: black;
      outline: none;
    }
    nav a[href="cadastro.html"] {
      border-left-color: black;
      background-color: #f0e68c;
    }
    main {
      margin-left: 180px;
      padding: 110px 20px 20px 20px;
      flex: 1;
    }
    form {
      max-width: 400px;
      background: #fff;
      padding: 20px;
      border-radius: 6px;
      box-shadow: 0 0 10px #ccc;
    }
    label {
      display: block;
      margin-top: 15px;
      font-weight: bold;
    }
    input[type="text"], input[type="tel"], select {
      width: 100%;
      padding: 8px;
      box-sizing: border-box;
      margin-top: 5px;
      border-radius: 4px;
      border: 1px solid #999;
    }
    button {
      margin-top: 20px;
      padding: 10px 15px;
      font-weight: bold;
      background-color: black;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background-color: #333;
    }
  </style>
</head>
<body>
  <header>Basson Aulas de Computação</header>
  <nav>
    <a href="cadastro.html">Cadastro</a>
    <a href="disciplinas.html">Disciplinas</a>
  </nav>
  <main>
    <h2>Cadastro de Usuário</h2>
    <form action="#" method="post">
      <label for="nome">Nome:</label>
      <input type="text" id="nome" name="nome" required />
      
      <label for="endereco">Endereço:</label>
      <input type="text" id="endereco" name="endereco" required />
      
      <label for="telefone">Telefone de Contato:</label>
      <input type="tel" id="telefone" name="telefone" required pattern="[0-9s-+()]{7,}" placeholder="Apenas números e símbolos + - ( )" />
      
      <label for="disciplina">Preferência por Disciplina:</label>
      <select id="disciplina" name="disciplina" required>
        <option value="">Selecione uma disciplina</option>
        <option value="calcular">História das máquinas de Calcular</option>
        <option value="calculo">História do cálculo</option>
        <option value="programacao">História da programação</option>
        <option value="computadores">História dos computadores</option>
        <option value="linux">História do sistema operacional Linux</option>
        <option value="circuitos">História dos circuitos eletrônicos</option>
        <option value="windows">História do sistema operacional Windows</option>
        <option value="escolas">História de algumas escolas de desenvolvimento para a Informática</option>
      </select>
      
      <button type="submit">Cadastrar</button>
    </form>
  </main>
</body>
</html>
<!-- disciplinas.html -->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Disciplinas - Basson Aulas de Computação</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #fffacd;
      display: flex;
      height: 100vh;
    }
    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      background: #fffacd;
      text-align: center;
      font-size: 2.5em;
      font-weight: bold;
      color: black;
      padding: 15px 0;
      box-shadow: 0 1px 3px rgba(0,0,0,0.1);
      z-index: 1000;
    }
    nav {
      background-color: #fffacd;
      padding-top: 90px;
      width: 180px;
      box-shadow: 1px 0 5px rgba(0,0,0,0.1);
      height: 100vh;
      box-sizing: border-box;
      position: fixed;
      top: 0;
      left: 0;
    }
    nav a {
      display: block;
      padding: 15px 20px;
      text-decoration: none;
      color: black;
      font-weight: bold;
      border-left: 5px solid transparent;
      transition: all 0.3s ease;
    }
    nav a:hover, nav a:focus {
      background-color: #f0e68c;
      border-left-color: black;
      outline: none;
    }
    nav a[href="disciplinas.html"] {
      border-left-color: black;
      background-color: #f0e68c;
    }
    main {
      margin-left: 180px;
      padding: 110px 20px 20px 20px;
      flex: 1;
    }
    ol {
      background: #fff;
      padding: 20px;
      border-radius: 6px;
      box-shadow: 0 0 10px #ccc;
      max-width: 600px;
    }
    ol li {
      margin-bottom: 12px;
      line-height: 1.4;
    }
  </style>
</head>
<body>
  <header>Basson Aulas de Computação</header>
  <nav>
    <a href="cadastro.html">Cadastro</a>
    <a href="disciplinas.html">Disciplinas</a>
  </nav>
  <main>
    <h2>Disciplinas</h2>
    <ol>
      <li>História das máquinas de Calcular</li>
      <li>História do cálculo</li>
      <li>História da programação</li>
      <li>História dos computadores</li>
      <li>História do sistema operacional Linux</li>
      <li>História dos circuitos eletrônicos</li>
      <li>História do sistema operacional Windows</li>
      <li>História de algumas escolas de desenvolvimento para a Informática</li>
    </ol>
  </main>
</body>
</html>
