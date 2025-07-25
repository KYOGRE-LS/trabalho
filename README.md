<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>Trabalho</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        
        /* Chat Button */
        #chatButton {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            font-size: 20px;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
            cursor: pointer;
        }


        #chatContainer {
            display: none;
            position: fixed;
            bottom: 80px;
            right: 20px;
            width: 250px;
            background-color: white;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
            overflow: hidden;
        }


        #chatHeader {
            background-color: #007bff;
            color: white;
            padding: 10px;
            cursor: pointer;
            text-align: center;
        }

        #chatBox {
            padding: 10px;
            height: 300px;
            overflow-y: scroll;
        }

        #userInputContainer {
            display: flex;
            border-top: 1px solid #ccc;
        }

        #userInput {
            flex: 1;
            padding: 10px;
            border: none;
        }


        #sendButton {
            padding: 10px;
            background-color: #007bff;
            color: white;
            cursor: pointer;
            border: none;
        }


        .user {
            text-align: right;
            color: blue;

        }


        .bot {
            text-align: left;
            color: green;
        }
    </style>
</head>

<body>

    <button id="chatButton" onclick="toggleChat()">&#x1F4AC</button>
    <div id="chatContainer" style="display:none;">
        <div id="chatHeader" onclick="toggleChat()">Prova de Informática</div>
        <div id="chatBox" style="height:200px; overflow-y:auto;"></div>
        <input type="text" id="userInput" placeholder="tipo de mensagem..." />
        <button id="sendButton" onclick="sendMessage()">enviar</button>
    </div>


    <script>
        function toggleChat() {
            let chatContainer = document.getElementById("chatContainer");
            chatContainer.style.display = (chatContainer.style.display == "none" || chatContainer.style.display == "") ? "block" : "none";
        }

        function sendMessage() {
            let userInput = document.getElementById("userInput").value;

            if (!userInput.trim()) return;

            document.getElementById("chatBox").innerHTML += "<p class='user'>Você: " + userInput + "</p>";
            document.getElementById("userInput").value = "";

            fetch("/get_response", {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: JSON.stringify({ message: userInput })
            })
                .then(response => response.json())
                .then(data => {
                    document.getElementById("chatBox").innerHTML += "<p class='bot'>Tony Stark: " + data.response + "</p>";
                    document.getElementById("chatBox").scrollTop = document.getElementById("chatBox").scrollHeight;
                });
        }
        function checkEnter(event) {
            if (event.key === "Enter") {
                sendMessage();  // Chama a função de envio quando o Enter é pressionado
            }
        }

        document.getElementById("userInput").addEventListener("keydown", checkEnter);

    </script>
    <header>
   <h1><hr>Transtorno do Espectro Autista – TEA (autismo)<hr></h1>
</header>
<nav>
    <a href="#">Início</a>
    <a href="#">Sobre</a>
    <a href="#">Serviços</a>
    <a href="#">Contato</a>
</nav>
<div class="main-content">
    <div class="content">
    <p>O Autismo (Transtorno do Espectro Autista – TEA) é um problema no desenvolvimento neurológico que prejudica a
    organização de pensamentos, sentimentos e emoções.</p>
    <p>Tem como características a dificuldade de comunicação por falta de domínio da linguagem e do uso da imaginação,
    a dificuldade de socialização e o comportamento limitado e repetitivo.</p>
    <p>Os sinais de alerta surgem nos primeiros meses de vida, mas a confirmação do diagnóstico costuma ocorrer aos
    dois ou três anos de idade.</p>
    <p>– Apresentar atraso anormal na fala;</p>
    <p>– Não responder quando for chamado e demonstrar desinteresse com as pessoas e objetos ao redor;</p>
    <p>– Ter dificuldades em participar de atividades e brincadeiras em grupo, preferindo sempre fazer tarefas sozinho;</p>
    <p>– Não conseguir interpretar gestos e expressões faciais;</p>
    <p>– Ter dificuldade para combinar palavras em frases ou repetir a mesma frase ou palavra com frequência;</p>
    <p>– Apresentar falta de filtro social (sinceridade excessiva);</p>
    <p>– Sentir incômodo diante de ambientes e situações sociais;</p>
    <p>– Ter seletividade em relação a cheiro, sabor e textura de alimentos;</p>
    <p>– Apresentar movimentos repetitivos e incomuns, como balançar o corpo para frente e para trás, bater as mãos, coçar algumas partes do corpo (como ouvidos, olhos e nariz), girar em torno de si, pular de forma repentina, reorganizar objetos em fileiras ou em cores;</p>
    <p>– Mostrar interesse obsessivo por assuntos considerados incomuns ou excêntricos, como biologia, paleontologia, tecnologia, datas, números, entre outros;</p>
    <p>– Ter problemas gastrointestinais ocasionados por quadros de ansiedade.</p>
    <p>Além disso, alguns autistas podem manifestar acessos de raiva, hiperatividade, passividade, déficit de atenção, dificuldades para lidar com ruídos, falta de empatia diante determinadas situações e aumento ou redução na resposta à dor e a temperaturas.</p>
    <p>De acordo com a forma como aparece, o TEA pode ser classificado em três tipos:</p>
    <p><b>– Autismo clássico:<br><br></b>Grau de comprometimento pode variar de muito. De maneira geral, os indivíduos são voltados para si mesmos, não estabelecem contato visual com as pessoas nem com o ambiente; conseguem falar, mas não usam a fala como ferramenta de comunicação. Embora possam entender enunciados simples, têm dificuldade de compreensão e apreendem apenas o sentido exato das palavras, não compreendendo o duplo sentido ou as comparações</p>
    <p>Nas formas mais graves, não demonstram qualquer contato interpessoal. São crianças isoladas, que não aprendem a falar, não olham para as outras pessoas nos olhos, não retribuem sorrisos, repetem movimentos sem muito significado ou ficam girando ao redor de si mesmas e apresentam deficiência mental importante.</p>
    <p><b>– Autismo de alto desempenho (também chamado de síndrome de Asperger):<br><br></b>Os portadores apresentam as mesmas dificuldades dos outros autistas, mas numa medida bem reduzida. São falantes e inteligentes, chegando a ser confundidos com gênios, porque são invencíveis nas áreas do conhecimento em que se especializam. Quanto menor a dificuldade de interação social, mais eles conseguem levar uma vida próxima à normal.</p>
    <p><b>– Distúrbio global do desenvolvimento sem outra especificação (DGD-SOE):<br><br></b>Os indivíduos são considerados dentro do espectro do autismo, com dificuldade de comunicação e de interação social, mas os sintomas não são suficientes para incluí-los em nenhuma das categorias específicas do transtorno, o que torna o diagnóstico muito mais difícil.</p>
    <p><b>Causas do autismo:<br><br></b>Atualmente pensa-se que há múltiplas causas para o autismo, entre elas, fatores genéticos, biológicos e ambientais. No entanto, saber o que ocorre com o cérebro dessas pessoas ainda é um mistério para a ciência.</p>
    <p><b>Tratamento:<br><br></b>O TEA ainda não tem cura e cada paciente exige um tipo de acompanhamento específico e individualizado que exige a participação dos pais, dos familiares e de uma equipe de diferentes profissionais, como médicos, fonoaudiólogos, fisioterapeutas, psicólogos e pedagogos, de forma a incentivar o indivíduo a realizar sozinho tarefas cotidianas, desenvolver formas de se comunicar socialmente e de ter maior estabilidade emocional.</p>
    <p><b>Recomendações para lidar com o autismo:</b></p>
    <p>– Ter em casa uma pessoa com formas graves de autismo pode representar um fator de desequilíbrio para toda a família. Por isso, todos os envolvidos precisam de atendimento e orientação especializados;</p>
    <p>– É fundamental descobrir um meio ou técnica, não importam quais, que possibilitem estabelecer algum tipo de comunicação com o autista;</p>
    <p>– Autistas têm dificuldade de lidar com mudanças, por menores que sejam; por isso é importante manter o seu mundo organizado e dentro da rotina;</p>
    <p>– Apesar de a tendência atual ser a inclusão de alunos com deficiência em escolas regulares, as limitações que o transtorno provoca devem ser respeitadas. Há casos em que o melhor é procurar uma instituição que ofereça atendimento mais individualizado.</p>
    </div>
    <div class="sidebar">
    <p><b>Fontes:</b><br>

Dr. Dráuzio Varella<br>
Hospital Israelita Albert Einstein: Blog Vida Saudável<br>
Ministério da Saúde<br>
Secretaria de Saúde do Paraná</p>
</div>
</div>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>

</body>

</html>
