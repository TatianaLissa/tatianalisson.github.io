<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Basson Aulas de Computação</title>
<style>
  body {
    margin: 0;
    background-color: #fff9b1; /* amarelo claro */
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    height: 100vh;
  }
  header {
    background: transparent;
    text-align: center;
    padding: 20px 0;
    color: black;
    font-weight: bold;
    font-size: 2em;
    user-select: none;
  }
  main {
    display: flex;
    flex: 1;
    min-height: 0;
  }
  nav {
    background: #ffe766;
    width: 250px;
    box-shadow: 2px 0 5px rgba(0,0,0,0.1);
    overflow-y: auto;
  }
  nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  nav li {
    border-bottom: 1px solid #ddd;
  }
  nav button {
    width: 100%;
    border: none;
    background: none;
    padding: 15px 20px;
    text-align: left;
    font-size: 1em;
    cursor: pointer;
    color: #333;
    transition: background-color 0.3s ease;
    outline-offset: -2px;
  }
  nav button:hover,
  nav button:focus {
    background-color: #fff176;
  }
  nav button.active {
    background-color: #ffd54f;
    font-weight: bold;
  }
  section.content {
    flex-grow: 1;
    padding: 20px;
    overflow-y: auto;
    background: white;
  }
  h2 {
    margin-top: 0;
    color: #333;
  }
  p {
    line-height: 1.5;
    color: #444;
  }
</style>
</head>
<body>

<header>Basson Aulas de Computação</header>

<main>
  <nav>
    <ul>
      <li><button aria-controls="tab1" class="active">História das Máquinas de Calcular</button></li>
      <li><button aria-controls="tab2">História do Cálculo</button></li>
      <li><button aria-controls="tab3">História da Programação</button></li>
      <li><button aria-controls="tab4">História dos Computadores</button></li>
      <li><button aria-controls="tab5">História do Sistema Operacional Linux</button></li>
      <li><button aria-controls="tab6">História dos Circuitos Eletrônicos</button></li>
      <li><button aria-controls="tab7">História do Sistema Operacional Windows</button></li>
      <li><button aria-controls="tab8">História das empresas Apple e Microsoft</button></li>
    </ul>
  </nav>

  <section class="content" id="tab1" role="tabpanel">
    <h2>História das Máquinas de Calcular</h2>
    <p>
      As máquinas de calcular surgiram como ferramentas mecânicas criadas para facilitar operações aritméticas básicas. 
      Um marco inicial foi a criação da régua de cálculo no século XVII, usada até o século XX. 
      Blaise Pascal desenvolveu em 1642 a Pascalina, considerada uma das primeiras calculadoras mecânicas.
      Depois dela, Antonio de Torres e Gottfried Wilhelm Leibniz aprimoraram as máquinas para somar, subtrair, multiplicar e dividir automaticamente.
      Essas invenções foram fundamentais para o desenvolvimento posterior dos computadores digitais.
    </p>
  </section>

  <section class="content" id="tab2" role="tabpanel" hidden>
    <h2>História do Cálculo</h2>
    <p>
      O cálculo matemático é uma área que teve grande desenvolvimento com Isaac Newton e Gottfried Leibniz no século XVII, independentemente e quase simultaneamente, 
      estabelecendo as bases do cálculo diferencial e integral. 
      Essa ciência permitiu o avanço em diversas áreas da física, engenharia e economia.
      O cálculo possibilitou modelar e resolver problemas envolvendo taxas de variação e acumulação, essenciais para a tecnologia e computação modernas.
    </p>
  </section>

  <section class="content" id="tab3" role="tabpanel" hidden>
    <h2>História da Programação</h2>
    <p>
      A programação começou com linguagens muito simples, como o código de máquina e assembly. 
      Ada Lovelace, reconhecida como a primeira programadora, desenvolveu algoritmos para a Máquina Analítica de Charles Babbage no século XIX.
      Com o avanço dos computadores eletrônicos na década de 1940, surgiram linguagens como Fortran e COBOL, que facilitaram o desenvolvimento de software.
      Hoje, linguagens modernas como Python e Java dominam, com foco em eficiência e facilidade de uso.
    </p>
  </section>

  <section class="content" id="tab4" role="tabpanel" hidden>
    <h2>História dos Computadores</h2>
    <p>
      Os primeiros computadores eram máquinas enormes feitas de componentes eletromecânicos. O ENIAC, criado em 1945, é considerado o primeiro computador eletrônico digital.
      A evolução seguiu com os computadores de válvulas, depois transistores e, finalmente, circuitos integrados a partir dos anos 60, levando aos microprocessadores.
      Essa rápida evolução transformou os computadores em dispositivos pessoais essenciais para trabalho, estudo e lazer.
    </p>
  </section>

  <section class="content" id="tab5" role="tabpanel" hidden>
    <h2>História do Sistema Operacional Linux</h2>
    <p>
      Desenvolvido por Linus Torvalds em 1991, o Linux é um sistema operacional de código aberto baseado no Unix.
      O Linux cresceu rapidamente devido à sua flexibilidade, estabilidade e custo zero, tornando-se popular em servidores, dispositivos embarcados e desktops.
      Distribuições como Ubuntu e Fedora tornaram o sistema acessível para usuários comuns e profissionais.
    </p>
  </section>

  <section class="content" id="tab6" role="tabpanel" hidden>
    <h2>História dos Circuitos Eletrônicos</h2>
    <p>
      Os circuitos eletrônicos têm suas raízes no desenvolvimento do diodo e transistor no século XX.
      A invenção do transistor em 1947 revolucionou eletrônica, permitindo a miniaturização e eficiência dos dispositivos.
      A partir daí, circuitos integrados surgiram na década de 1960, possibilitando a construção dos modernos computadores e dispositivos móveis.
    </p>
  </section>

  <section class="content" id="tab7" role="tabpanel" hidden>
    <h2>História do Sistema Operacional Windows</h2>
    <p>
      Criado pela Microsoft, o Windows foi lançado em 1985 como uma interface gráfica para o MS-DOS, facilitando o uso de computadores pessoais.
      Suas versões evoluíram ao longo dos anos, do Windows 3.1, 95, XP, até o Windows 10 e 11 atuais, tornando-se um sistema dominante no mercado de PCs.
      O Windows trouxe interfaces amigáveis, suporte a multimídia e integração com redes globais.
    </p>
  </section>

  <section class="content" id="tab8" role="tabpanel" hidden>
    <h2>História das empresas Apple e Microsoft</h2>
    <p>
      Apple e Microsoft são duas gigantes da tecnologia que influenciaram profundamente a computação pessoal.
      A Apple, fundada em 1976, popularizou o computador pessoal com o Apple II e depois o Macintosh, focando no design e inovação.
      Microsoft, também criada em 1975, tornou-se líder com seu sistema operacional Windows e software como Office.
      Ambas as empresas continuam em competição e colaboração, moldando a indústria de tecnologia.
    </p>
  </section>
</main>

<script>
  const buttons = document.querySelectorAll('nav button');
  const tabs = document.querySelectorAll('section.content');

  buttons.forEach(button => {
    button.addEventListener('click', () => {
      const targetId = button.getAttribute('aria-controls');

      // atualiza visibilidade das abas
      tabs.forEach(tab => {
        tab.hidden = tab.id !== targetId;
      });

      // atualiza botão ativo
      buttons.forEach(btn => btn.classList.remove('active'));
      button.classList.add('active');
    });
  });
</script>

</body>
</html>
