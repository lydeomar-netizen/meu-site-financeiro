<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Planilha MultCap - Controle Financeiro</title>
    <style>
        :root {
            --cor-fundo: #0f172a;
            --cor-card: #1e293b;
            --cor-texto: #f8fafc;
            --cor-texto-mutado: #94a3b8;
            --cor-primaria: #00b4d8;
            --cor-sucesso: #10b981;
            --cor-perigo: #ef4444;
            --border-padrao: 1px solid #334155;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, sans-serif;
        }

        body {
            background-color: var(--cor-fundo);
            color: var(--cor-texto);
            padding: 20px;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            margin-bottom: 30px;
        }

        header h1 {
            color: var(--cor-primaria);
            font-size: 28px;
        }

        header p {
            color: var(--cor-texto-mutado);
            font-size: 14px;
        }

        /* Painel de Saldos */
        .dashboard {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .card {
            background-color: var(--cor-card);
            padding: 20px;
            border-radius: 8px;
            border: var(--border-padrao);
        }

        .card h3 {
            font-size: 14px;
            color: var(--cor-texto-mutado);
            text-transform: uppercase;
            margin-bottom: 10px;
        }

        .card .valor {
            font-size: 24px;
            font-weight: bold;
        }

        .card.receitas .valor { color: var(--cor-sucesso); }
        .card.despesas .valor { color: var(--cor-perigo); }
        .card.saldo .valor { color: var(--cor-primaria); }

        /* Formulário e Histórico */
        .conteudo {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 20px;
        }

        @media (max-width: 768px) {
            .conteudo { grid-template-columns: 1fr; }
        }

        .bloco {
            background-color: var(--cor-card);
            padding: 20px;
            border-radius: 8px;
            border: var(--border-padrao);
            height: fit-content;
        }

        .bloco h2 {
            font-size: 18px;
            margin-bottom: 20px;
            border-bottom: var(--border-padrao);
            padding-bottom: 10px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            font-size: 14px;
            margin-bottom: 5px;
            color: var(--cor-texto-mutado);
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 10px;
            background-color: var(--cor-fundo);
            border: var(--border-padrao);
            border-radius: 6px;
            color: var(--cor-texto);
            font-size: 14px;
        }

        .btn-salvar {
            width: 100%;
            padding: 12px;
            background-color: var(--cor-primaria);
            color: white;
            border: none;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.2s;
        }

        .btn-salvar:hover {
            background-color: #0077b6;
        }

        /* Tabela de Transações */
        .tabela-container {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            text-align: left;
        }

        th, td {
            padding: 12px;
            border-bottom: var(--border-padrao);
            font-size: 14px;
        }

        th {
            color: var(--cor-texto-mutado);
            font-weight: 600;
        }

        .tipo-entrada { color: var(--cor-sucesso); font-weight: bold; }
        .tipo-saida { color: var(--cor-perigo); font-weight: bold; }

        .btn-deletar {
            background: none;
            border: none;
            color: var(--cor-perigo);
            cursor: pointer;
            font-size: 14px;
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <h1>Planilha MultCap Financeira</h1>
            <p>Organize suas receitas, despesas e saldo em tempo real</p>
        </header>

        <!-- Indicadores de Saldos -->
        <section class="dashboard">
            <div class="card receitas">
                <h3>Total Receitas</h3>
                <div class="valor" id="total-receitas">R$ 0,00</div>
            </div>
            <div class="card despesas">
                <h3>Total Despesas</h3>
                <div class="valor" id="total-despesas">R$ 0,00</div>
            </div>
            <div class="card saldo">
                <h3>Saldo Atual</h3>
                <div class="valor" id="saldo-atual">R$ 0,00</div>
            </div>
        </section>

        <!-- Área de Interação -->
        <div class="conteudo">
            <!-- Formulário -->
            <aside class="bloco">
                <h2>Nova Transação</h2>
                <form id="finance-form">
                    <div class="form-group">
                        <label for="descricao">Descrição</label>
                        <input type="text" id="descricao" placeholder="Ex: Salário, Mercado, Luz" required>
                    </div>
                    <div class="form-group">
                        <label for="valor">Valor (R$)</label>
                        <input type="number" id="valor" step="0.01" placeholder="0,00" required>
                    </div>
                    <div class="form-group">
                        <label for="tipo">Tipo</label>
                        <select id="tipo" required>
                            <option value="entrada">Receita (+) </option>
                            <option value="saida">Despesa (-)</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="categoria">Categoria</label>
                        <select id="categoria" required>
                            <option value="Moradia">Moradia</option>
                            <option value="Alimentação">Alimentação</option>
                            <option value="Transporte">Transporte</option>
                            <option value="Lazer">Lazer</option>
                            <option value="Salário">Salário / Renda</option>
                            <option value="Outros">Outros</option>
                        </select>
                    </div>
                    <button type="submit" class="btn-salvar">Adicionar Registro</button>
                </form>
            </aside>

            <!-- Histórico -->
            <main class="bloco">
                <h2>Histórico de Lançamentos</h2>
                <div class="tabela-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Descrição</th>
                                <th>Categoria</th>
                                <th>Valor</th>
                                <th>Ação</th>
                            </tr>
                        </thead>
                        <tbody id="lista-transacoes">
                            <!-- Inserido dinamicamente via JS -->
                        </tbody>
                    </table>
                </div>
            </main>
        </div>
    </div>

    <script>
        // Gerenciamento de Estado dos Dados (Salva no navegador do usuário)
        let transacoes = JSON.parse(localStorage.getItem('multcap_transacoes')) || [];

        const form = document.getElementById('finance-form');
        const listaTransacoes = document.getElementById('lista-transacoes');
        const txtReceitas = document.getElementById('total-receitas');
        const txtDespesas = document.getElementById('total-despesas');
        const txtSaldo = document.getElementById('saldo-atual');

        function atualizarDados() {
            listaTransacoes.innerHTML = '';
            let receitas = 0;
            let despesas = 0;

            transacoes.forEach((t, index) => {
                const valorFormatado = t.valor.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
                const classeTipo = t.tipo === 'entrada' ? 'tipo-entrada' : 'tipo-saida';
                const sinal = t.tipo === 'entrada' ? '+' : '-';

                if (t.tipo === 'entrada') receitas += t.valor;
                else despesas += t.valor;

                const tr = document.createElement('tr');
                tr.innerHTML = `
                    <td>${t.descricao}</td>
                    <td>${t.categoria}</td>
                    <td class="${classeTipo}">${sinal} ${valorFormatado}</td>
                    <td><button class="btn-deletar" onclick="removerTransacao(${index})">❌</button></td>
                `;
                listaTransacoes.appendChild(tr);
            });

            const saldo = receitas - despesas;

            txtReceitas.innerText = receitas.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
            txtDespesas.innerText = despesas.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
            txtSaldo.innerText = saldo.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });

            localStorage.setItem('multcap_transacoes', JSON.stringify(transacoes));
        }

        form.addEventListener('submit', (e) => {
            e.preventDefault();

            const novaTransacao = {
