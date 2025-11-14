body {
    background-color: #1D4221; /* Verde Floresta */
    color: white;
    font-family: "Bai Jamjuree", sans-serif;
    /* Centralização do Conteúdo */
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh; /* Ocupa a altura total da viewport */
    margin: 0;
    padding: 20px;
}

main {
    text-align: center;
    max-width: 600px; /* Limita a largura da caixa de conteúdo */
    width: 100%;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5); /* Sombra suave */
}

/* Estilo do Parágrafo */
main p {
    font-size: 1.1em;
    line-height: 1.6;
    margin-bottom: 25px;
}

/* Estilo dos Botões */
button {
    background-color: #64A712; /* Verde Vibrante */
    color: white;
    font-family: "Bai Jamjuree", sans-serif;
    border: none;
    border-radius: 8px; /* Cantos arredondados */
    padding: 12px 20px;
    margin: 10px auto; /* Centraliza e adiciona espaço */
    cursor: pointer;
    transition: background-color 0.3s, transform 0.1s;
    font-size: 1em;
    width: 90%; /* Ocupa a largura total para melhor clique */
    display: block;
}

button:hover {
    background-color: #79C21A; /* Escurece um pouco ao passar o mouse */
    transform: translateY(-2px); /* Efeito de elevação sutil */
}

.passo {
    display: none;
}

.passo.ativo {
    display: block;
}

img {
    max-width: 100%; /* Garante responsividade */
    height: auto;
    border-radius: 8px;
    margin-bottom: 20px;
}
2. index.html (Com Botões de Reinício)
Atualize o Passo 4 e o Passo 11 com o botão de reinício:

Linha 40 (Passo 4):

HTML

        <div class="passo" id="passo-4">
            <img src="img/cenario-passo4-voltar-casa.png" alt="imagem voltando para casa e desitindo da aventura">
            <p>Você decide que a aventura é grande demais e volta para casa, mas sempre se pergunta o que teria
                encontrado.</p>
            <button class="btn-proximo" data-proximo="0">Recomeçar Aventura</button>
        </div>
Linha 80 (Passo 11):

HTML

        <div class="passo" id="passo-11">
            <img src="img/cenario-passo11-cidade-perdida.png" alt="encontrando uma cidade maravilhosa perdida no Amazonas">
            <p>Dentro da cidade perdida, você descobre tesouros inimagináveis e decide se dedicar a estudar e preservar
                este lugar</p>
            <button class="btn-proximo" data-proximo="0">Começar uma Nova Aventura</button>
        </div>
3. script.js (Melhorado)
JavaScript

// Renomeado para melhor clareza: botoesProximo
const botoesProximo = document.querySelectorAll('.btn-proximo');

botoesProximo.forEach(button => {
    button.addEventListener('click', function(){
        // Usa const e let para escopo correto
        const atual = document.querySelector('.passo.ativo');
        
        // Obtém o número do passo e constrói o ID de forma segura
        const idProximo = this.getAttribute('data-proximo');
        const proximoPasso = 'passo-' + idProximo;

        // Verifica se o elemento atual existe antes de tentar remover a classe
        if (atual) {
            atual.classList.remove('ativo');
        }
        
        // Ativa o próximo passo, que agora pode ser o passo-0 (reinício)
        const proximoElemento = document.getElementById(proximoPasso);
        if (proximoElemento) {
            proximoElemento.classList.add('ativo');
        }
    })
})












































































































