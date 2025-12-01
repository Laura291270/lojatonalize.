# lojatonalize.
loja de base tonalize com variedade de cores de base 
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resultado | Sua Base Tonalize</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header><a href="selection.html" class="back-link">← Testar Outra</a><div class="logo">TONALIZE</div></header>

    <section class="final-result">
        <h2>🎉 Seu Tom Escolhido: Match Perfeito!</h2>
        
        <div id="result-box" class="result-box">
            <div class="final-tone-display">
                <h1 id="final-code">T-25W</h1>
                <p id="final-desc">Tom Médio | Subtom Quente</p>
            </div>
            <p>Comprovado no provador virtual: o seu tom desaparece na sua pele, garantindo um acabamento natural e radiante. Você tem a garantia de match perfeito!</p>
            <a href="#" class="cta-button">Comprar T-25W Agora</a>
            <p class="small-text">Frete grátis para o seu primeiro Match!</p>
        </div>
    </section>
    
    <script>
        // Funções de simulação de cores e dados para a página de resultado
        function getSimulatedColor(code) {
            if (code.includes('T-48W')) return '#6A3F2C'; 
            if (code.includes('T-05C')) return '#F8E7E0';
            if (code.includes('T-25W')) return '#D3A78D';
            if (code.includes('T-15N')) return '#EAC0A6';
            if (code.includes('T-38C')) return '#4B271B';
            return '#C5917D';
        }
        
        // Lógica para extrair os dados da URL e preencher o resultado
        const urlParams = new URLSearchParams(window.location.search);
        const toneCode = urlParams.get('tone') || 'T-25W'; // Padrão se não houver parâmetro

        if (toneCode) {
            document.getElementById('final-code').textContent = toneCode;
            document.querySelector('.final-tone-display').style.backgroundColor = getSimulatedColor(toneCode);
            
            const subtom = toneCode.endsWith('W') ? 'Subtom Quente' : (toneCode.endsWith('C') ? 'Subtom Frio' : 'Subtom Neutro');
            const range = (parseInt(toneCode.substring(2)) < 15) ? 'Claro' : ((parseInt(toneCode.substring(2)) < 35) ? 'Médio' : 'Profundo');
            
            document.getElementById('final-desc').textContent = Tom ${range} | ${subtom};
            document.querySelector('.cta-button').textContent = Comprar ${toneCode} Agora;
        }
    </script>
</body>
</html>
