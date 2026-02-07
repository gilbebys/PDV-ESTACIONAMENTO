<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>GILVAN PARK </title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/jsbarcode@3.11.5/dist/JsBarcode.all.min.js"></script>
    <script src="https://cdn.sheetjs.com/xlsx-0.20.0/package/dist/xlsx.full.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap');
        body { font-family: 'Inter', sans-serif; background: #0f172a; color: rgb(246, 248, 247); height: 100vh; overflow: hidden; }
        .tab-content { display: none; height: 100%; }
        .tab-content.active { display: block; }
        input, select, textarea { color: #00060c !important; font-weight: bold; border-radius: 6px; }
        
        /* Botão Flutuante Excel */
        .fab { position: fixed; bottom: 30px; right: 30px; z-index: 100; }
        .fab-menu { display: none; position: absolute; bottom: 70px; right: 0; flex-direction: column; gap: 10px; }
        .fab:hover .fab-menu { display: flex; }

        @media print {
            @page { size: 80mm auto; margin: 0; }
            body * { visibility: hidden; }
            #ticket-print, #ticket-print * { visibility: visible; display: block !important; }
            #ticket-print { 
                position: absolute; left: 0; top: 0; width: 72mm; padding: 4mm;
                color: #000; background: #fff; font-family: 'Courier New', monospace; font-size: 12px;
            }
            .cut-line { border-top: 1px dashed #000; margin-top: 20mm; }
        }
    </style>
</head>
<body class="flex flex-col">

    <header class="bg-slate-900 p-4 flex justify-between items-center border-b-2 border-emerald-500">
        <div class="flex items-center gap-4">
            <span class="bg-emerald-500 text-black font-black px-2 py-0.5 rounded text-[10px]">SISTEMA</span>
            <h1 class="font-black text-xl italic text-emerald-500 uppercase">PARK<span class="text-white">GILVAN</span></h1>
        </div>
        <div id="relogio" class="font-mono text-xl font-bold text-emerald-400">00:00:00</div>
        <button onclick="abrirGaveta()" class="bg-orange-500 text-black font-black px-4 py-2 rounded-lg text-xs hover:bg-orange-400 transition">?? ABRIR GAVETA</button>
    </header>

    <div class="flex flex-1 overflow-hidden">
        <aside class="w-96 bg-slate-800 border-r border-slate-700 p-4 flex flex-col gap-4 overflow-y-auto">
            
            <div class="bg-slate-900 p-5 rounded-3xl border border-emerald-500 shadow-2xl">
                <label class="text-[9px] font-black text-emerald-400 uppercase block mb-1">PLACA OU QR-SELO</label>
                <input id="inputPrincipal" type="text" placeholder="ABC1234" class="w-full bg-white rounded-xl p-4 text-4xl font-black text-center uppercase outline-none focus:ring-4 ring-emerald-500/20">
                <button onclick="processarFluxo()" class="w-full mt-3 bg-emerald-500 text-black font-black py-4 rounded-xl text-sm uppercase italic hover:bg-emerald-400">PROCESSAR</button>
            </div>

            <div id="painelSaida" class="hidden bg-slate-900 p-5 rounded-3xl border border-blue-500 shadow-2xl animate-pulse-slow">
                <div class="flex justify-between items-center mb-3">
                    <h2 id="outPlaca" class="text-3xl font-black italic text-blue-400">---</h2>
                    <button onclick="fecharSaida()" class="text-slate-500 text-xl font-bold">?</button>
                </div>
                
                <div class="bg-slate-800 rounded-2xl p-4 text-center mb-3">
                    <p id="outPermanencia" class="text-[10px] text-slate-400 font-bold uppercase mb-1"></p>
                    <div class="flex items-center justify-center gap-1">
                        <span class="text-xl font-bold text-slate-500">R$</span>
                        <input id="outValor" type="number" step="0.01" oninput="calcTroco()" class="bg-transparent text-4xl font-black text-white w-full text-center outline-none">
                    </div>
                </div>

                <div class="grid grid-cols-2 gap-2 mb-3">
                    <button onclick="setValorTabela()" class="bg-slate-700 p-2 rounded text-[9px] font-black uppercase">VALOR TABELA</button>
                    <button onclick="setValorProRataAvulso()" class="bg-blue-600 p-2 rounded text-[9px] font-black uppercase italic">CALC. PRO-RATA</button>
                </div>

                <div class="space-y-2 mb-4 bg-slate-800/50 p-3 rounded-xl border border-emerald-500/30">
                    <label class="text-[9px] font-black text-emerald-400 uppercase">Recebido (Dinheiro)</label>
                    <input id="valRecebido" type="number" step="0.01" placeholder="0,00" oninput="calcTroco()" class="w-full p-2 rounded-lg text-center font-bold text-2xl bg-white">
                    <div class="flex justify-between items-center px-1 mt-1">
                        <span class="text-[10px] font-black text-slate-400 uppercase">TROCO:</span>
                        <span id="labelTroco" class="text-2xl font-black text-emerald-400">R$ 0,00</span>
                    </div>
                </div>

                <div class="grid grid-cols-3 gap-1">
                    <button onclick="finalizarPagamento('DINHEIRO')" class="bg-emerald-600 p-3 rounded-lg text-[8px] font-black uppercase">DINHEIRO</button>
                    <button onclick="finalizarPagamento('PIX')" class="bg-blue-600 p-3 rounded-lg text-[8px] font-black uppercase">PIX</button>
                    <button onclick="finalizarPagamento('CARTÃO')" class="bg-slate-700 p-3 rounded-lg text-[8px] font-black uppercase">CARTÃO</button>
                </div>
            </div>

            <div class="mt-auto bg-slate-900 p-5 rounded-3xl border border-slate-700">
                <div id="caixaFechado">
                    <h3 class="text-[10px] font-black text-slate-500 mb-2 uppercase">Abertura de Turno</h3>
                    <input id="opNome" placeholder="NOME DO OPERADOR" class="w-full p-2 rounded-lg mb-2 text-xs uppercase bg-white">
                    <input id="opFundo" type="number" placeholder="VALOR INICIAL R$" class="w-full p-2 rounded-lg mb-3 text-xs bg-white">
                    <button onclick="abrirCaixa()" class="w-full bg-emerald-500 text-black py-3 rounded-xl font-black text-[10px] uppercase">ABRIR CAIXA</button>
                </div>
                <div id="caixaAberto" class="hidden text-center">
                    <p id="infoOp" class="text-[10px] text-emerald-400 font-black mb-1 uppercase"></p>
                    <h2 id="saldoCaixa" class="text-3xl font-black text-emerald-400 italic">R$ 0,00</h2>
                    <button onclick="fecharCaixa()" class="w-full mt-2 bg-red-600/20 text-red-500 border border-red-500/50 py-2 rounded-lg font-black text-[9px] uppercase hover:bg-red-600 hover:text-white transition">FECHAR CAIXA (X-READ)</button>
                </div>
            </div>
        </aside>

        <main class="flex-1 flex flex-col overflow-hidden">
            <nav class="bg-slate-900 p-3 flex gap-2 border-b border-slate-700">
                <button onclick="changeTab('patios', this)" class="tab-btn bg-emerald-500 text-black px-6 py-2 rounded-xl font-black text-[10px] uppercase italic">Patios</button>
                <button onclick="changeTab('mensalistas', this)" class="tab-btn text-slate-400 px-6 py-2 rounded-xl font-black text-[10px] uppercase italic">Mensalistas</button>
                <button onclick="changeTab('convenios', this)" class="tab-btn text-slate-400 px-6 py-2 rounded-xl font-black text-[10px] uppercase italic">Convenios</button>
                <button onclick="changeTab('financeiro', this)" class="tab-btn text-slate-400 px-6 py-2 rounded-xl font-black text-[10px] uppercase italic">Financeiro</button>
                <button onclick="changeTab('config', this)" class="tab-btn text-slate-400 px-6 py-2 rounded-xl font-black text-[10px] uppercase italic">Config</button>
            </nav>

            <div class="flex-1 overflow-auto p-6">
                
                <div id="tab-patios" class="tab-content active">
                    <div class="grid grid-cols-2 gap-8 h-full">
                        <div class="bg-slate-800/40 p-6 rounded-[2.5rem] border border-slate-700">
                            <h3 class="text-[11px] font-black text-slate-500 uppercase mb-4 italic tracking-widest">? Patio Clientes Avulsos</h3>
                            <div id="gridAvulso" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-3"></div>
                        </div>
                        <div class="bg-emerald-500/5 p-6 rounded-[2.5rem] border border-emerald-500/20">
                            <h3 class="text-[11px] font-black text-emerald-500 uppercase mb-4 italic tracking-widest">? Patio Mensalistas</h3>
                            <div id="gridMensal" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-3"></div>
                        </div>
                    </div>
                </div>

                <div id="tab-mensalistas" class="tab-content">
                    <div class="grid grid-cols-12 gap-6">
                        <div class="col-span-4 bg-slate-800 p-6 rounded-[2.5rem] border border-slate-700 space-y-2">
                            <h3 id="mFormTitle" class="text-[10px] font-black text-emerald-400 uppercase italic">Novo Cadastro Mensal</h3>
                            <input id="mId" type="hidden">
                            <input id="mPlaca" placeholder="PLACAS (EX: ABC1234, DEF5678)" class="w-full p-2 rounded-lg text-lg font-bold uppercase bg-white">
                            <input id="mNome" placeholder="NOME COMPLETO" class="w-full p-2 rounded text-xs bg-white uppercase">
                            <input id="mCPF" placeholder="CPF (OBRIGATORIO)" class="w-full p-2 rounded text-xs bg-white">
                            <div class="grid grid-cols-2 gap-2">
                                <input id="mTel" placeholder="TELEFONE" class="p-2 rounded text-xs bg-white">
                                <input id="mEmail" placeholder="E-MAIL" class="p-2 rounded text-xs bg-white">
                            </div>
                            <textarea id="mEnd" placeholder="ENDEREÇO COMPLETO" class="w-full p-2 rounded text-xs bg-white uppercase h-16"></textarea>
                            <div class="grid grid-cols-3 gap-1">
                                <input id="mModelo" placeholder="MODELO" class="p-2 rounded text-[10px] bg-white uppercase">
                                <input id="mCor" placeholder="COR" class="p-2 rounded text-[10px] bg-white uppercase">
                                <input id="mAno" placeholder="ANO" class="p-2 rounded text-[10px] bg-white">
                            </div>
                            <label class="text-[9px] font-bold text-slate-500 uppercase">Data de Vencimento:</label>
                            <input id="mVenc" type="date" class="w-full p-3 rounded-xl font-black text-emerald-600 bg-white">
                            <button onclick="salvarMensalista()" class="w-full bg-emerald-500 text-black py-4 rounded-xl font-black text-xs uppercase mt-2">SALVAR CADASTRO</button>
                        </div>
                        <div id="listaMensalistas" class="col-span-8 grid grid-cols-1 gap-3 content-start"></div>
                    </div>
                </div>

                <div id="tab-convenios" class="tab-content">
                    <div class="grid grid-cols-12 gap-6">
                        <div class="col-span-4 bg-slate-800 p-6 rounded-[2.5rem] border border-blue-500/30">
                            <h3 class="text-[10px] font-black text-blue-400 uppercase mb-4 italic">Cadastrar Convenio/Loja</h3>
                            <input id="sLoja" placeholder="NOME DA LOJA" class="w-full p-3 rounded-xl mb-2 text-xs font-bold uppercase bg-white">
                            <input id="sDesc" type="number" placeholder="DESCONTO %" class="w-full p-3 rounded-xl mb-4 text-xs font-bold bg-white">
                            <button onclick="salvarSelo()" class="w-full bg-blue-500 text-black py-4 rounded-xl font-black text-xs uppercase italic">GERAR SELO CONVENIADO</button>
                        </div>
                        <div id="listaSelos" class="col-span-8 grid grid-cols-2 gap-4"></div>
                    </div>
                </div>

                <div id="tab-financeiro" class="tab-content">
                    <div class="grid grid-cols-12 gap-6 h-full">
                        <div class="col-span-3 space-y-4">
                            <div class="bg-slate-800 p-6 rounded-3xl border border-emerald-500/30">
                                <h4 class="text-[10px] font-black text-emerald-500 uppercase mb-4">Fluxo por Metodo</h4>
                                <div id="resumoMetodos" class="space-y-2"></div>
                            </div>
                            <div class="bg-slate-800 p-6 rounded-3xl border border-slate-700">
                                <h4 class="text-[10px] font-black text-slate-400 uppercase mb-2">Total no Turno</h4>
                                <h2 id="totalFinanceiroGeral" class="text-3xl font-black text-white">R$ 0,00</h2>
                            </div>
                        </div>
                        <div class="col-span-9 bg-slate-800 rounded-[2.5rem] border border-slate-700 p-6 flex flex-col">
                            <h4 class="text-[10px] font-black text-slate-500 uppercase mb-4">Historico de Vendas e Pagamentos</h4>
                            <div class="flex-1 overflow-y-auto">
                                <table class="w-full text-left text-[11px]">
                                    <thead class="bg-slate-900 text-emerald-400 sticky top-0">
                                        <tr>
                                            <th class="p-3">DATA/HORA</th>
                                            <th class="p-3">PLACA</th>
                                            <th class="p-3">METODO</th>
                                            <th class="p-3">VALOR</th>
                                            <th class="p-3">OPERADOR</th>
                                        </tr>
                                    </thead>
                                    <tbody id="tabelaVendasCorpo" class="divide-y divide-slate-700"></tbody>
                                </table>
                            </div>
                        </div>
                    </div>
                </div>

                <div id="tab-config" class="tab-content">
                    <div class="grid grid-cols-2 gap-6">
                        <div class="bg-slate-800 p-6 rounded-3xl border border-blue-500/30">
                            <h3 class="text-[10px] font-black text-blue-400 uppercase mb-3 italic">Tabela Avulso e Pro-Rata</h3>
                            <label class="text-[9px] text-slate-400 uppercase">Valor Hora Base (Calculo Pro-Rata Minuto):</label>
                            <input id="confValorHora" type="number" step="0.01" class="w-full p-2 mb-4 bg-white" onchange="salvarConfigGeral()">
                            <h4 class="text-[9px] font-black text-white uppercase mb-2">Tabela de Faixas (Cheia):</h4>
                            <div id="listaFaixasAvulso" class="space-y-2 mb-4"></div>
                            <button onclick="adicionarFaixa()" class="bg-blue-500/20 text-blue-400 px-4 py-2 rounded text-[10px] font-black">+ NOVA FAIXA</button>
                        </div>
                        <div class="bg-slate-800 p-6 rounded-3xl border border-purple-500/30">
                            <h3 class="text-[10px] font-black text-purple-400 uppercase mb-3 italic">Tabela Mensalista (Pro-Rata 30 Dias)</h3>
                            <div class="flex gap-2 mb-4">
                                <input id="valMensalRef" type="number" value="480.00" class="w-full p-2 rounded-lg font-black text-purple-600 bg-white">
                                <button onclick="gerarTabelaMensal()" class="bg-purple-600 px-6 rounded-lg font-black text-[10px] text-white">ATUALIZAR TABELA</button>
                            </div>
                            <div id="previewMensal" class="grid grid-cols-6 gap-1 max-h-64 overflow-y-auto p-2 bg-black/20 rounded-xl"></div>
                        </div>
                    </div>
                </div>

            </div>
        </main>
    </div>

    <div class="fab group">
        <div class="fab-menu">
            <button onclick="exportarExcel('vendas')" class="bg-emerald-600 text-white p-4 rounded-full shadow-2xl font-black text-xs hover:scale-110 transition">VENDAS (XLSX)</button>
            <button onclick="exportarExcel('caixa')" class="bg-blue-600 text-white p-4 rounded-full shadow-2xl font-black text-xs hover:scale-110 transition">CAIXA (XLSX)</button>
            <button onclick="window.print()" class="bg-slate-700 text-white p-4 rounded-full shadow-2xl font-black text-xs hover:scale-110 transition">IMPRIMIR TELA</button>
        </div>
        <button class="bg-emerald-500 text-black w-16 h-16 rounded-full shadow-2xl flex items-center justify-center font-black text-2xl hover:bg-emerald-400 transition ring-4 ring-emerald-500/20">??</button>
    </div>

    <div id="ticket-print"></div>

    <script>
        let db = {
            patio: JSON.parse(localStorage.getItem('gp52_patio')) || [],
            vendas: JSON.parse(localStorage.getItem('gp52_vendas')) || [],
            mensalistas: JSON.parse(localStorage.getItem('gp52_mensal')) || [],
            selos: JSON.parse(localStorage.getItem('gp52_selos')) || [],
            caixas: JSON.parse(localStorage.getItem('gp52_caixas')) || [],
            config: JSON.parse(localStorage.getItem('gp52_config')) || {
                valorHora: 20.00,
                tabelaAvulso: [{min: 60, valor: 20.00}],
                tabelaMensal: {},
                empresa: { nome: "GILVAN PARK", cnpj: "00.000.000/0001-00", end: "AVENIDA CENTRAL, 500", tel: "31 99999-9999" }
            }
        };

        let caixaAtivo = JSON.parse(localStorage.getItem('gp52_caixa_ativo')) || null;
        let vSaindo = null;
        let vCalc = { tabela: 0, prorata: 0 };

        function salvar() {
            localStorage.setItem('gp52_patio', JSON.stringify(db.patio));
            localStorage.setItem('gp52_vendas', JSON.stringify(db.vendas));
            localStorage.setItem('gp52_mensal', JSON.stringify(db.mensalistas));
            localStorage.setItem('gp52_selos', JSON.stringify(db.selos));
            localStorage.setItem('gp52_caixas', JSON.stringify(db.caixas));
            localStorage.setItem('gp52_config', JSON.stringify(db.config));
            localStorage.setItem('gp52_caixa_ativo', JSON.stringify(caixaAtivo));
        }

        // --- CAIXA ---
        function abrirCaixa() {
            const op = document.getElementById('opNome').value.toUpperCase();
            const fundo = parseFloat(document.getElementById('opFundo').value) || 0;
            if(!op) return alert("Identifique o operador!");
            caixaAtivo = { operador: op, saldo: fundo, fundo: fundo, inicio: new Date().toISOString() };
            db.caixas.push({ ...caixaAtivo, tipo: 'ABERTURA' });
            salvar(); renderCaixa();
        }
        function fecharCaixa() {
            if(confirm("Deseja fechar o caixa e gerar relatorio final?")) {
                db.caixas.push({ ...caixaAtivo, tipo: 'FECHAMENTO', fim: new Date().toISOString() });
                caixaAtivo = null; salvar(); renderCaixa();
            }
        }
        function renderCaixa() {
            if(caixaAtivo) {
                document.getElementById('caixaFechado').classList.add('hidden');
                document.getElementById('caixaAberto').classList.remove('hidden');
                document.getElementById('saldoCaixa').innerText = `R$ ${caixaAtivo.saldo.toFixed(2)}`;
                document.getElementById('infoOp').innerText = `OPERADOR: ${caixaAtivo.operador}`;
            } else {
                document.getElementById('caixaFechado').classList.remove('hidden');
                document.getElementById('caixaAberto').classList.add('hidden');
            }
        }

        // --- FINANCEIRO VISUAL ---
        function renderFinanceiro() {
            const corpo = document.getElementById('tabelaVendasCorpo');
            const resumo = document.getElementById('resumoMetodos');
            const totalGeral = document.getElementById('totalFinanceiroGeral');
            
            corpo.innerHTML = db.vendas.slice().reverse().map(v => `
                <tr class="hover:bg-slate-700/50">
                    <td class="p-3 text-slate-400">${new Date(v.data).toLocaleString()}</td>
                    <td class="p-3 font-black">${v.placa}</td>
                    <td class="p-3 font-bold text-blue-400">${v.metodo}</td>
                    <td class="p-3 font-black text-emerald-400">R$ ${v.valor.toFixed(2)}</td>
                    <td class="p-3 text-slate-500">${v.op}</td>
                </tr>
            `).join('');

            const totais = db.vendas.reduce((acc, v) => {
                acc[v.metodo] = (acc[v.metodo] || 0) + v.valor;
                acc.geral = (acc.geral || 0) + v.valor;
                return acc;
            }, {geral: 0});

            const metodos = ['DINHEIRO', 'PIX', 'CARTÃO', 'MENSALIDADE'];
            resumo.innerHTML = metodos.map(m => `
                <div class="flex justify-between p-2 bg-slate-900/50 rounded-lg">
                    <span class="text-[10px] text-slate-500 font-bold">${m}</span>
                    <span class="font-black text-white">R$ ${(totais[m] || 0).toFixed(2)}</span>
                </div>
            `).join('');
            totalGeral.innerText = `R$ ${totais.geral.toFixed(2)}`;
        }

        // --- OPERACIONAL ---
        function processarFluxo() {
            const input = document.getElementById('inputPrincipal').value.toUpperCase().trim();
            if(!input) return;

            // Logica de Selo QR de Desconto
            if(input.startsWith("SELO-")) {
                if(!vSaindo) return alert("Selecione um veiculo no patio primeiro!");
                const perc = parseFloat(input.split("-")[2]);
                let v = parseFloat(document.getElementById('outValor').value);
                document.getElementById('outValor').value = (v * (1 - perc/100)).toFixed(2);
                calcTroco(); alert(`Desconto de ${perc}% aplicado!`);
            } else {
                const m = db.mensalistas.find(x => x.placa.split(',').map(p => p.trim()).includes(input));
                const pAtivo = db.patio.find(x => x.placa === input);
                if(pAtivo) abrirCheckout(pAtivo); 
                else registrarEntrada(input, m ? 'MENSAL' : 'AVULSO');
            }
            document.getElementById('inputPrincipal').value = "";
        }

        function registrarEntrada(placa, tipo) {
            const v = { id: Date.now(), placa, entrada: new Date().toISOString(), tipo };
            db.patio.push(v); salvar(); renderPatios();
            imprimirTicket(v, 'TICKET DE ENTRADA');
        }

        function abrirCheckout(v) {
            vSaindo = v;
            const min = Math.ceil(Math.abs(new Date() - new Date(v.entrada)) / 60000);
            
            if(v.tipo === 'AVULSO') {
                const faixa = db.config.tabelaAvulso.find(f => min <= f.min) || db.config.tabelaAvulso[db.config.tabelaAvulso.length-1];
                vCalc.tabela = faixa ? parseFloat(faixa.valor) : (min/60 * db.config.valorHora);
                vCalc.prorata = (min * (db.config.valorHora / 60));
                document.getElementById('outValor').value = vCalc.tabela.toFixed(2);
            } else {
                vCalc.tabela = 0; vCalc.prorata = 0;
                document.getElementById('outValor').value = "0.00";
            }

            document.getElementById('outPlaca').innerText = v.placa;
            document.getElementById('outPermanencia').innerText = `${min} MINUTOS (${v.tipo})`;
            document.getElementById('painelSaida').classList.remove('hidden');
            document.getElementById('valRecebido').value = "";
            calcTroco();
        }

        function finalizarPagamento(metodo) {
            if(!caixaAtivo) return alert("Abra o caixa para operar!");
            const val = parseFloat(document.getElementById('outValor').value);
            db.vendas.push({ placa: vSaindo.placa, valor: val, metodo, tipo: vSaindo.tipo, data: new Date().toISOString(), op: caixaAtivo.operador });
            caixaAtivo.saldo += val;
            db.patio = db.patio.filter(x => x.id !== vSaindo.id);
            abrirGaveta(); salvar(); renderPatios(); renderCaixa(); fecharSaida(); renderFinanceiro();
            imprimirTicket({placa: vSaindo.placa, valor: val, metodo}, 'RECIBO DE SAIDA');
        }

        // --- MENSALISTA PRO-RATA ---
        function pagarMensalidade(id) {
            const m = db.mensalistas.find(x => x.id == id);
            const dias = prompt(`MENSALISTA: ${m.nome}\nQuantos dias de PRO-RATA o cliente deseja pagar?`, "30");
            
            if(dias && !isNaN(dias)) {
                const d = parseInt(dias);
                const valorCobrar = parseFloat(db.config.tabelaMensal[d] || 0);
                const metodo = prompt("Forma de Pagamento (DINHEIRO, PIX, CARTÃO):", "PIX").toUpperCase();
                
                if(confirm(`Confirmar R$ ${valorCobrar.toFixed(2)} por ${d} dias?`)) {
                    db.vendas.push({ placa: m.placa, valor: valorCobrar, metodo, tipo: 'MENSAL', data: new Date().toISOString(), op: caixaAtivo.operador });
                    if(caixaAtivo) caixaAtivo.saldo += valorCobrar;
                    
                    let dt = new Date(m.vencimento); if(isNaN(dt)) dt = new Date();
                    dt.setDate(dt.getDate() + d);
                    m.vencimento = dt.toISOString().split('T')[0];

                    salvar(); renderMensalistas(); renderCaixa(); renderFinanceiro();
                    imprimirReciboMensal(m, valorCobrar, d, metodo);
                }
            }
        }

        // --- MENSALISTAS CRUD ---
        function salvarMensalista() {
            const m = {
                id: document.getElementById('mId').value || Date.now(),
                placa: document.getElementById('mPlaca').value.toUpperCase(),
                nome: document.getElementById('mNome').value.toUpperCase(),
                cpf: document.getElementById('mCPF').value,
                tel: document.getElementById('mTel').value,
                email: document.getElementById('mEmail').value,
                end: document.getElementById('mEnd').value.toUpperCase(),
                modelo: document.getElementById('mModelo').value.toUpperCase(),
                cor: document.getElementById('mCor').value.toUpperCase(),
                ano: document.getElementById('mAno').value,
                vencimento: document.getElementById('mVenc').value
            };
            if(!m.placa || !m.cpf) return alert("Placa e CPF sÃo obrigatorios!");
            
            const index = db.mensalistas.findIndex(x => x.id == m.id);
            if(index > -1) db.mensalistas[index] = m;
            else db.mensalistas.push(m);
            
            salvar(); renderMensalistas(); limparFormMensal();
        }

        function editarMensalista(id) {
            const m = db.mensalistas.find(x => x.id == id);
            document.getElementById('mId').value = m.id;
            document.getElementById('mPlaca').value = m.placa;
            document.getElementById('mNome').value = m.nome;
            document.getElementById('mCPF').value = m.cpf;
            document.getElementById('mTel').value = m.tel;
            document.getElementById('mEmail').value = m.email;
            document.getElementById('mEnd').value = m.end;
            document.getElementById('mModelo').value = m.modelo;
            document.getElementById('mCor').value = m.cor;
            document.getElementById('mAno').value = m.ano;
            document.getElementById('mVenc').value = m.vencimento;
            document.getElementById('mFormTitle').innerText = "Editando Cadastro";
        }

        // --- IMPRESSÃO (80MM / CODIGO DE BARRAS / CORTE) ---
        function imprimirTicket(v, modo) {
            const area = document.getElementById('ticket-print');
            area.innerHTML = `
                <div style="text-align:center">
                    <b style="font-size:16px">${db.config.empresa.nome}</b><br>
                    ${db.config.empresa.cnpj}<br>${db.config.empresa.end}<br>
                    ------------------------------------------<br>
                    <b>${modo}</b><br>
                    <h1 style="font-size:40px; margin:10px 0;">${v.placa}</h1>
                    <div style="display:flex; justify-content:center"><svg id="barcode-ticket"></svg></div>
                    <br>ENTRADA: ${new Date().toLocaleString()}<br>
                    ${v.valor ? `<b>TOTAL PAGO: R$ ${v.valor.toFixed(2)}</b><br>METODO: ${v.metodo}` : ''}
                    <br><br>Obrigado pela preferencia!
                    <div class="cut-line">.</div>
                </div>`;
            JsBarcode("#barcode-ticket", v.placa, { height: 40, displayValue: false });
            setTimeout(() => { window.print(); area.innerHTML = ""; }, 400);
        }

        function imprimirReciboMensal(m, v, d, met) {
            const area = document.getElementById('ticket-print');
            area.innerHTML = `
                <div style="text-align:center">
                    <b>RECIBO DE MENSALIDADE</b><br>
                    ------------------------------------------<br>
                    CLIENTE: ${m.nome}<br>
                    VEICULO(S): ${m.placa}<br>
                    VALOR: R$ ${v.toFixed(2)} (${met})<br>
                    PERIODO: ${d} DIAS ADICIONADOS<br>
                    NOVO VENCIMENTO: ${m.vencimento}<br>
                    ------------------------------------------<br>
                    OPERADOR: ${caixaAtivo.operador}<br>
                    ${new Date().toLocaleString()}
                    <div class="cut-line">.</div>
                </div>`;
            setTimeout(() => { window.print(); area.innerHTML = ""; }, 400);
        }

        function imprimirCredencial(m) {
            const area = document.getElementById('ticket-print');
            area.innerHTML = `
                <div style="text-align:center; border: 2px solid #000; padding: 10px;">
                    <b>CREDENCIAL MENSALISTA</b><br>
                    <h1 style="font-size:35px">${m.placa.split(',')[0]}</h1>
                    <b>${m.nome}</b><br>
                    CPF: ${m.cpf}<br>
                    <div style="display:flex; justify-content:center; margin-top:10px"><svg id="barcode-m"></svg></div>
                    <div class="cut-line">.</div>
                </div>`;
            JsBarcode("#barcode-m", m.placa.split(',')[0], { height: 40, displayValue: false });
            setTimeout(() => { window.print(); area.innerHTML = ""; }, 400);
        }

        // --- CONVENIOS ---
        function salvarSelo() {
            const s = { id: Date.now(), loja: document.getElementById('sLoja').value.toUpperCase(), desc: document.getElementById('sDesc').value };
            db.selos.push(s); salvar(); renderSelos();
        }

        function imprimirSeloQR(s) {
            const area = document.getElementById('ticket-print');
            area.innerHTML = `<div style="text-align:center"><b>DESCONTO CONVENIADO</b><br>${s.loja}<br><div id="qrcode-box" style="display:inline-block; margin:15px"></div><br><b style="font-size:18px">${s.desc}% OFF</b><div class="cut-line">.</div></div>`;
            new QRCode(document.getElementById("qrcode-box"), { text: `SELO-${s.id}-${s.desc}`, width: 150, height: 150 });
            setTimeout(() => { window.print(); area.innerHTML = ""; }, 500);
        }

        // --- EXPORTAR EXCEL ---
        function exportarExcel(t) {
            const ws = XLSX.utils.json_to_sheet(t === 'vendas' ? db.vendas : db.caixas);
            const wb = XLSX.utils.book_new(); XLSX.utils.book_append_sheet(wb, ws, "DADOS");
            XLSX.writeFile(wb, `GILVAN_PARK_${t.toUpperCase()}.xlsx`);
        }

        // --- UI GERAL ---
        function renderPatios() {
            document.getElementById('gridAvulso').innerHTML = db.patio.filter(x => x.tipo === 'AVULSO').map(v => `<div onclick="abrirCheckoutPlaca('${v.placa}')" class="bg-white text-black p-4 rounded-xl text-center font-black cursor-pointer shadow-lg hover:bg-emerald-100 transition">${v.placa}</div>`).join('');
            document.getElementById('gridMensal').innerHTML = db.patio.filter(x => x.tipo === 'MENSAL').map(v => `<div onclick="abrirCheckoutPlaca('${v.placa}')" class="bg-emerald-500 text-black p-4 rounded-xl text-center font-black cursor-pointer shadow-lg hover:bg-emerald-400 transition">${v.placa}</div>`).join('');
        }

        function renderMensalistas() {
            document.getElementById('listaMensalistas').innerHTML = db.mensalistas.map(m => `
                <div class="bg-slate-800 p-4 rounded-2xl border border-slate-700 flex justify-between items-center">
                    <div>
                        <b class="text-emerald-400 text-lg uppercase">${m.placa}</b>
                        <p class="text-xs text-white uppercase">${m.nome} | VENCE: ${m.vencimento}</p>
                    </div>
                    <div class="flex gap-1">
                        <button onclick="pagarMensalidade(${m.id})" class="bg-emerald-600 text-white px-3 py-2 rounded-lg text-[9px] font-black italic">PAGAR PRO-RATA</button>
                        <button onclick='imprimirCredencial(${JSON.stringify(m)})' class="bg-slate-700 text-white px-3 py-2 rounded-lg text-[9px] font-black italic">CREDENTIAL</button>
                        <button onclick="editarMensalista(${m.id})" class="bg-blue-600 text-white px-2 py-2 rounded-lg text-[9px] font-black uppercase">EDITAR</button>
                    </div>
                </div>`).join('');
        }

        function renderSelos() {
            document.getElementById('listaSelos').innerHTML = db.selos.map(s => `
                <div class="bg-white text-black p-4 rounded-2xl flex justify-between items-center shadow-lg">
                    <div><b class="uppercase">${s.loja}</b><p class="text-blue-600 font-black text-xl">${s.desc}% OFF</p></div>
                    <button onclick='imprimirSeloQR(${JSON.stringify(s)})' class="bg-slate-900 text-white px-4 py-2 rounded-lg text-[9px] font-black uppercase">IMPRIMIR QR</button>
                </div>`).join('');
        }

        function gerarTabelaMensal() {
            const ref = parseFloat(document.getElementById('valMensalRef').value);
            for(let i=1; i<=30; i++) db.config.tabelaMensal[i] = ((ref/30)*i).toFixed(2);
            renderConfig(); salvar();
        }

        function renderConfig() {
            document.getElementById('confValorHora').value = db.config.valorHora;
            let h = "";
            for(let i=1; i<=30; i++) h += `<div class="p-1 bg-slate-700 rounded text-[9px] text-center">D${i}: ${db.config.tabelaMensal[i]||'0'}</div>`;
            document.getElementById('previewMensal').innerHTML = h;
            document.getElementById('listaFaixasAvulso').innerHTML = db.config.tabelaAvulso.map((f, i) => `
                <div class="flex gap-2">
                    <input type="number" value="${f.min}" onchange="db.config.tabelaAvulso[${i}].min=this.value;salvar()" class="w-20 p-1 text-[10px]" placeholder="Min">
                    <input type="number" value="${f.valor}" onchange="db.config.tabelaAvulso[${i}].valor=this.value;salvar()" class="w-24 p-1 text-[10px]" placeholder="R$">
                </div>`).join('');
        }

        function calcTroco() {
            const t = parseFloat(document.getElementById('outValor').value) || 0;
            const r = parseFloat(document.getElementById('valRecebido').value) || 0;
            document.getElementById('labelTroco').innerText = "R$ " + (r - t > 0 ? (r - t).toFixed(2) : "0,00");
        }

        function setValorTabela() { document.getElementById('outValor').value = vCalc.tabela.toFixed(2); calcTroco(); }
        function setValorProRataAvulso() { document.getElementById('outValor').value = vCalc.prorata.toFixed(2); calcTroco(); }
        function abrirGaveta() { alert("COMANDO ENVIADO: GAVETA ABERTA"); }
        function fecharSaida() { document.getElementById('painelSaida').classList.add('hidden'); }
        function abrirCheckoutPlaca(p) { abrirCheckout(db.patio.find(x => x.placa === p)); }
        function limparFormMensal() { document.querySelectorAll('#tab-mensalistas input, #tab-mensalistas textarea').forEach(i => i.value = ""); document.getElementById('mFormTitle').innerText = "Novo Cadastro Mensal"; }
        function adicionarFaixa() { db.config.tabelaAvulso.push({min: 0, valor: 0}); renderConfig(); }
        function salvarConfigGeral() { db.config.valorHora = parseFloat(document.getElementById('confValorHora').value); salvar(); }

        function changeTab(id, btn) {
            document.querySelectorAll('.tab-content').forEach(t => t.classList.remove('active'));
            document.getElementById('tab-' + id).classList.add('active');
            document.querySelectorAll('.tab-btn').forEach(b => b.className = "tab-btn text-slate-400 px-6 py-2 rounded-xl font-black text-[10px] uppercase italic");
            btn.className = "tab-btn bg-emerald-500 text-black px-6 py-2 rounded-xl font-black text-[10px] uppercase italic shadow-lg";
            if(id === 'financeiro') renderFinanceiro();
        }

        setInterval(() => document.getElementById('relogio').innerText = new Date().toLocaleTimeString(), 1000);
        renderCaixa(); renderPatios(); renderMensalistas(); renderSelos(); renderConfig();
    </script>
</body>
</html>
