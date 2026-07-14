<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Planilha de Organização Financeira e Renda Fixa</title>
    <style>
        /* Estilos Gerais e Cores Inspiradas na Identidade de Finanças */
        :root {
            --cor-principal: #00b4d8; /* Azul moderno/tecnológico */
            --cor-escura: #0f172a; /* Fundo escuro premium */
            --cor-secundaria: #1e293b; /* Variação de fundo */
            --cor-texto: #f8fafc;
            --cor-texto-mutado: #94a3b8;
            --cor-destaque: #10b981; /* Verde para botões e sucesso */
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--cor-escura);
            color: var(--cor-texto);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            padding: 20px 0;
            border-bottom: 1px solid #334155;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: var(--cor-principal);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Seção Hero (Principal) */
        .hero {
            padding: 80px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 42px;
            line-height: 1.2;
            margin-bottom: 20px;
            color: #ffffff;
        }

        .hero h1 span {
            color: var(--cor-principal);
        }

        .hero p {
            font-size: 18px;
            color: var(--cor-texto-mutado);
            max-width: 700px;
            margin: 0 auto 40px auto;
        }

        /* Botão de Ação */
        .btn-cta {
            display: inline-block;
            background-color: var(--cor-destaque);
            color: white;
            padding: 18px 36px;
            font-size: 18px;
            font-weight: bold;
            text-decoration: none;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);
            transition: transform 0.2s, background-color 0.2s;
        }

        .btn-cta:hover {
            transform: translateY(-2px);
            background-color: #059669;
        }

        .sub-cta {
            font-size: 14px;
            color: var(--cor-texto-mutado);
            margin-top: 10px;
        }

        /* Seção de Recursos/Benefícios */
        .features {
            background-color: var(--cor-secundaria);
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 32px;
            margin-bottom: 50px;
        }

        .grid-features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background-color: var(--cor-escura);
            padding: 30px;
            border-radius: 12px;
            border: 1px solid #334155;
        }

        .feature-card h3 {
            font-size: 20px;
            color: var(--cor-principal);
            margin-bottom: 15px;
        }

        .feature-card p {
            color: var(--cor-texto-mutado);
            font-size: 15px;
        }

        /* Seção O Que Você Vai Receber */
        .whats-inside {
            padding: 80px 0;
        }

        .inside-list {
            max-width: 600px;
            margin: 0 auto;
            list-style: none;
        }

        .inside-list li {
            font-size: 18px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }

        .inside-list li::before {
            content: "✓";
            color: var(--cor-destaque);
            font-weight: bold;
            font-size: 20px;
            margin-right: 15px;
        }

        /* FAQ (Perguntas Frequentes) */
        .faq {
            background-color: var(--cor-secundaria);
            padding: 80px 0;
        }

        .faq-item {
            max-width: 800px;
            margin: 0 auto 20px auto;
            background-color: var(--cor-escura);
            padding: 20px;
            border-radius: 8px;
        }

        .faq-item h4 {
            font-size: 18px;
            margin-bottom: 10px;
            color: var(--cor-texto);
        }

        .faq-item p {
            color: var(--cor-texto-mutado);
            font-size: 15px;
        }

        /* Rodapé */
        footer {
            padding: 40px 0;
            text-align: center;
            color: var(--cor-texto-mutado);
            font-size: 14px;
            border-top: 1px solid #334155;
        }

        /* Responsividade básica */
        @media (max-width: 768px) {
            .hero h1 { font-size: 32px; }
            .hero p { font-size: 16px; }
        }
    </style>
</head>
<body>

    <!-- Cabeçalho simples -->
    <header>
        <div class="container">
            <div class="logo">MultiCap Clone</div>
        </div>
    </header>

    <!-- Seção Principal de Vendas -->
    <section class="hero">
        <div class="container">
            <h1>Organize suas finanças e monte sua carteira de <span>Renda Fixa</span> do zero</h1>
            <p>Monitore seus gastos diários, trace metas financeiras claras e descubra como gerar renda passiva todos os meses sem precisar de planilhas complexas ou jargões do mercado.</p>
            <a href="SEU_LINK_DE_DOWNLOAD_OU_COMPRA_AQUI" class="btn-cta">Quero Baixar a Planilha Agora</a>
            <div class="sub-cta">Acesso imediato e 100% seguro</div>
        </div>
    </section>

    <!-- Benefícios e Recursos -->
    <section class="features">
        <div class="container">
            <h2 class="section-title">O que você vai conseguir resolver</h2>
            <div class="grid-features">
                <div class="feature-card">
                    <h3>Fim do Caos Financeiro</h3>
                    <p>Saiba exatamente para onde vai cada centavo do seu dinheiro no final do mês através de categorias visuais simplificadas.</p>
                </div>
                <div class="feature-card">
                    <h3>Simulador de Renda Passiva</h3>
                    <p>Planeje sua independência calculando o quanto você precisa investir hoje para ter a renda mensal que deseja no futuro.</p>
                </div>
                <div class="feature-card">
                    <h3>Foco em Renda Fixa</h3>
                    <p>Aprenda a mapear e organizar seus títulos (CDBs, Tesouro Direto, LCIs) em um único dashboard unificado.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Conteúdo Prático -->
    <section class="whats-inside">
        <div class="container">
            <h2 class="section-title">O que está incluso no material?</h2>
            <ul class="inside-list">
                <li>Painel de controle financeiro mensal e anual estruturado.</li>
                <li>Gráficos automáticos de evolução de patrimônio.</li>
                <li>Calculadora integrada de juros compostos.</li>
                <li>Acesso vitalício para atualizações do modelo.</li>
            </ul>
            <div style="text-align: center; margin-top: 40px;">
                <a href="SEU_LINK_DE_DOWNLOAD_OU_COMPRA_AQUI" class="btn-cta">Garantir Meu Acesso Grátis</a>
            </div>
        </div>
    </section>

    <!-- Perguntas Frequentes -->
    <section class="faq">
        <div class="container">
            <h2 class="section-title">Dúvidas Frequentes</h2>
            <div class="faq-item">
                <h4>Preciso ser um especialista em Excel para usar?</h4>
                <p>Não. A planilha foi desenvolvida para ser totalmente automatizada. Você só preenche seus gastos e o sistema gera os gráficos sozinho.</p>
            </div>
            <div class="faq-item">
                <h4>Como vou receber o arquivo?</h4>
                <p>Assim que clicar no botão de download, você será direcionado para baixar a cópia oficial diretamente no seu computador ou celular.</p>
            </div>
        </div>
    </section>

    <!-- Rodapé legal -->
    <footer>
        <div class="container">
            <p>&copy; 2026 - Página Inspirada no Modelo MultiCap. Todos os direitos reservados.</p>
        </div>
    </footer>

</body>
</html>
