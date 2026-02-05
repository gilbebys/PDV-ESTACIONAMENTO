<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GILVAN PARK - </title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/jsbarcode@3.11.5/dist/JsBarcode.all.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap');
        body { font-family: 'Inter', sans-serif; background-color: #f3f4f6; }
        
        .window-style { background: #e0e0e0; border: 1px solid #999; box-shadow: inset 1px 1px white, 2px 2px 5px rgba(0,0,0,0.2); }
        .grid-pro-rata { display: grid; grid-template-columns: repeat(5, 1fr); gap: 4px; padding: 10px; background: #d4d4d4; border: 1px solid #888; }
        .cell-pro-rata { display: flex; align-items: center; background: white; border: 1px solid #999; font-size: 11px; height: 24px; }
        .cell-label { background: #eee; width: 45px; border-right: 1px solid #999; display: flex; align-items: center; justify-content: center; font-weight: bold; color: #444; }
        .cell-value { flex: 1; padding-left: 5px; font-family: monospace; color: #000; }

        @media print {
            body * { display: none !important; }
            #areaImpressao, #areaImpressao * { display: block !important; visibility: visible !important; }
            #areaImpressao { position: absolute; left: 0; top: 0; width: 72mm; text-align: center; }
        }
        .tab-content { display: none; }
        .tab-content.active { display: block; }
    </style>
</head>
<body class="h-screen flex flex-col overflow-hidden text-slate-900">

    <header class="bg-slate-900 text-white px-6 py-3 flex justify-between items-center border-b-2 border-emerald-500 shadow-lg">
        <div class="flex items-center gap-3">
            <span class="bg-emerald-500 text-black px-2 py-0.5 rounded font-black text-[10px]">GP</span>
            <h1 class="text-lg font-bold tracking-tight uppercase">GILVAN PARK</h1>
        </div>
        <div id="relogio" class="font-mono text-xl font-bold bg-slate-800 px-3 py-1 rounded border border-slate-700">00:00:00</div>
    </header>

    <div class="flex flex-1 overflow-hidden">
        <aside class="w-80 bg-white border-r p-5 flex flex-col gap-4 overflow-y-auto shadow-inner">
            <div class="bg-slate-900 p-5 rounded-2xl text-white">
                <label class="text-[9px] font-bold text-emerald-400 uppercase tracking-widest">Entrada / Saída de Veículo</label>
                <input id="inputPrincipal" type="text" autofocus 
                    class="w-full bg-slate-800 border border-slate-700 rounded-xl p-3 text-2xl font-black text-center uppercase mt-1 outline-none focus:border-emerald-500" 
                    placeholder="PLACA" onkeyup="if(event.key === 'Enter') processarFluxo()">
                <button onclick="processarFluxo()" class="w-full mt-3 bg-emerald-500 text-black py-3 rounded-xl font-bold text-xs uppercase hover:bg-emerald-400">Confirmar</button>
            </div>

            <div id="painelSaida" class="hidden bg-blue-700 rounded-2xl p-5 text-white shadow-xl">
                <div class="flex justify-between items-start mb-2">
                    <h2 id="outPlaca" class="text-3xl font-black italic">---</h2>
                    <span id="badgeStatus" class="text-[9px] px-2 py-1 rounded font-bold"></span>
                </div>
                <div class="bg-white p-4 rounded-xl text-center my-3">
                    <div id="outValor" class="text-4xl font-black text-slate-900">R$ 0,00</div>
                    <span id="outTempo" class="text-[10px] font-bold text-blue-600 uppercase italic">0 MINUTOS</span>
                </div>
                
                <div class="bg-blue-800/50 p-3 rounded-xl mb-3 border border-blue-400/20">
                    <input id="valorRecebido" type="number" oninput="calcularTroco()" placeholder="RECEBIDO R$"
                        class="w-full bg-white text-slate-900 rounded-lg p-2 font-bold text-lg text-center outline-none">
                    <div id="displayTroco" class="text-emerald-300 font-bold text-center mt-1 text-xs uppercase">TROCO: R$ 0,00</div>
                </div>

                <div class="grid grid-cols-2 gap-2">
                    <button onclick="finalizar('DINHEIRO')" class="bg-slate-900 p-3 rounded-lg font-bold text-[9px] uppercase">Dinheiro</button>
                    <button onclick="finalizar('PIX')" class="bg-slate-900 p-3 rounded-lg font-bold text-[9px] uppercase">PIX</button>
                    <button onclick="finalizar('DEBITO')" class="bg-white text-black p-3 rounded-lg font-bold text-[9px] uppercase">Débito</button>
                    <button onclick="finalizar('CREDITO')" class="bg-white text-black p-3 rounded-lg font-bold text-[9px] uppercase">Crédito</button>
                    <button id="btnIsentar" onclick="finalizar('MENSALISTA')" class="hidden col-span-2 bg-emerald-500 text-black p-3 rounded-lg font-black text-[9px] uppercase">Liberar Mensalista</button>
                </div>
                <button onclick="cancelarSaida()" class="w-full mt-3 text-[9px] font-bold uppercase opacity-60">Cancelar</button>
            </div>

            <div class="mt-auto bg-slate-100 p-4 rounded-xl border border-slate-200">
                <span class="text-[9px] font-bold text-slate-400 uppercase">Caixa em Dinheiro</span>
                <h2 id="valorEmCaixa" class="text-2xl font-black text-slate-900">R$ 0,00</h2>
                <button onclick="abrirFecharCaixa()" id="btnCaixa" class="w-full mt-3 bg-slate-900 text-white py-3 rounded-xl font-bold text-[10px] uppercase">Abrir Turno</button>
            </div>
        </aside>

        <main class="flex-1 flex flex-col overflow-hidden">
            <nav class="flex gap-1 p-3 bg-white border-b shadow-sm z-10 overflow-x-auto">
                <button onclick="changeTab('operacao')" class="tab-btn px-5 py-2 rounded-lg font-bold text-xs bg-emerald-500 text-white">PÁTIO</button>
                <button onclick="changeTab('mensalistas')" class="tab-btn px-5 py-2 rounded-lg font-bold text-xs text-slate-500">MENSALISTAS</button>
                <button onclick="changeTab('selos')" class="tab-btn px-5 py-2 rounded-lg font-bold text-xs text-slate-500">CONVÊNIOS/SELOS</button>
                <button onclick="changeTab('config')" class="tab-btn px-5 py-2 rounded-lg font-bold text-xs text-slate-500">TABELAS DE PREÇO</button>
                <button onclick="changeTab('relatorios')" class="tab-btn px-5 py-2 rounded-lg font-bold text-xs text-slate-500">RELATÓRIOS</button>
            </nav>

            <div class="flex-1 overflow-auto p-6">
                <div id="tab-operacao" class="tab-content active">
                    <div id="gridPatio" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4"></div>
                </div>

                <div id="tab-mensalistas" class="tab-content">
                    <div class="grid grid-cols-1 md:grid-cols-12 gap-6">
                        <div class="md:col-span-4 bg-white p-6 rounded-2xl border shadow-sm">
                            <h3 class="font-bold text-xs uppercase mb-4 text-emerald-600">Cadastro de Mensalista</h3>
                            <div class="space-y-2">
                                <input id="mNome" placeholder="NOME COMPLETO" class="w-full p-2 border rounded-lg text-xs uppercase font-semibold">
                                <input id="mCPF" placeholder="CPF (APENAS NÚMEROS)" class="w-full p-2 border rounded-lg text-xs font-semibold">
                                <input id="mTel" placeholder="TELEFONE" class="w-full p-2 border rounded-lg text-xs font-semibold">
                                <input id="mEmail" placeholder="E-MAIL" class="w-full p-2 border rounded-lg text-xs font-semibold">
                                <input id="mEnd" placeholder="ENDEREÇO" class="w-full p-2 border rounded-lg text-xs uppercase font-semibold">
                                <div class="grid grid-cols-2 gap-2">
                                    <input id="mPlaca" placeholder="PLACA" class="w-full p-2 border rounded-lg text-xs font-black uppercase">
                                    <input id="mVenc" type="date" class="w-full p-2 border rounded-lg text-xs font-semibold">
                                </div>
                                <button onclick="cadastrarMensalista()" class="w-full bg-slate-900 text-white py-3 rounded-xl font-bold text-[10px] uppercase">Ativar Mensalista</button>
                            </div>
                        </div>
                        <div id="cardsMensalistas" class="md:col-span-8 grid grid-cols-1 lg:grid-cols-2 gap-3"></div>
                    </div>
                </div>

                <div id="tab-selos" class="tab-content">
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        <div class="bg-white p-6 rounded-2xl border shadow-sm h-fit">
                            <h3 class="font-bold text-xs uppercase mb-4 text-emerald-600 italic">Cadastrar Loja/Convênio</h3>
                            <input id="sNome" placeholder="NOME DA LOJA" class="w-full p-3 border rounded-xl text-xs uppercase font-bold mb-3">
                            <input id="sDesc" type="number" placeholder="DESCONTO %" class="w-full p-3 border rounded-xl text-xs font-bold mb-3">
                            <button onclick="cadastrarSelo()" class="w-full bg-slate-950 text-white py-4 rounded-xl font-bold text-[10px] uppercase">Gerar Ticket de Convênio</button>
                        </div>
                        <div id="listaSelos" class="md:col-span-2 grid grid-cols-1 lg:grid-cols-2 gap-3"></div>
                    </div>
                </div>

                <div id="tab-config" class="tab-content">
                    <div class="max-w-4xl mx-auto window-style p-1 rounded">
                        <div class="bg-slate-800 text-white text-[10px] px-2 py-1 flex justify-between items-center mb-4">
                            <span>Cadastro e edição de Tabelas de preços para mensalistas</span>
                            <span class="bg-red-600 px-1 text-white cursor-pointer">X</span>
                        </div>

                        <div class="grid grid-cols-1 md:grid-cols-12 gap-4 p-2">
                            <div class="md:col-span-3 border border-slate-400 bg-white h-64 overflow-y-auto">
                                <div class="bg-blue-800 text-white text-[10px] px-2 py-0.5">Tabela Atual</div>
                                <div class="p-2 text-[10px] font-bold">Mensalistas Ativos</div>
                            </div>

                            <div class="md:col-span-7 border border-slate-400 p-3 bg-[#f0f0f0]">
                                <div class="mb-4 flex gap-4">
                                    <div class="flex-1">
                                        <p class="text-[9px] bg-slate-300 border border-slate-400 px-2 text-center uppercase font-bold">Nome da Tabela</p>
                                        <input type="text" value="MENSALISTAS" class="w-full border border-slate-400 text-[10px] px-1 h-6 outline-none bg-white" readonly>
                                    </div>
                                    <div class="w-24">
                                        <p class="text-[9px] bg-slate-300 border border-slate-400 px-2 text-center uppercase font-bold">Valor Mensal R$</p>
                                        <input id="precoMensalInput" type="number" step="0.01" class="w-full border border-slate-400 text-[10px] px-1 h-6 text-center font-bold bg-white outline-emerald-500" oninput="gerarTabelaReferencia()">
                                    </div>
                                </div>
                                <p class="text-[10px] font-bold mb-1">Grade Pro Rata (Diário)</p>
                                <div id="tabelaProRataFisica" class="grid-pro-rata"></div>
                            </div>

                            <div class="md:col-span-2 flex flex-col gap-2">
                                <button onclick="salvarTabelaMensal()" class="window-style text-[10px] py-2 bg-emerald-500 text-white font-bold">SALVAR</button>
                                <button onclick="changeTab('operacao')" class="window-style text-[10px] py-1 bg-white">Sair</button>
                            </div>
                        </div>
                    </div>

                    <div class="mt-8 bg-white p-6 rounded-2xl border shadow-sm max-w-4xl mx-auto">
                        <div class="flex justify-between items-center mb-4">
                            <h3 class="text-[10px] font-bold uppercase text-slate-400">Preços Rotativo</h3>
                            <button onclick="adicionarFracao()" class="bg-emerald-500 text-black px-4 py-2 rounded-xl font-bold text-[10px] uppercase">+ Adicionar Faixa</button>
                        </div>
                        <div id="tarifarioContainer" class="grid grid-cols-2 md:grid-cols-5 gap-4"></div>
                    </div>
                </div>

                <div id="tab-relatorios" class="tab-content">
                    <div class="bg-white p-6 rounded-2xl border shadow-sm">
                        <div class="flex justify-between items-center mb-6">
                            <select id="filtroAno" onchange="atualizarRelatorios()" class="border p-2 rounded text-xs"></select>
                            <button onclick="exportarExcel()" class="bg-emerald-600 text-white px-6 py-2 rounded-xl text-xs font-bold uppercase">Baixar Relatório CSV</button>
                        </div>
                        <div class="h-[400px]"><canvas id="graficoVendas"></canvas></div>
                    </div>
                </div>
            </div>
        </main>
    </div>

    <div id="areaImpressao" class="hidden">
        <div style="text-align:center; font-family:monospace; padding:10px;">
            <div id="ticketCorpo"></div>
            <div style="display:flex; justify-content:center; margin:15px 0;" id="qrContainer"></div>
            <div style="display:flex; justify-content:center; margin:10px 0;"><svg id="barContainer"></svg></div>
        </div>
    </div>

    <script>
        let db = {
            patio: JSON.parse(localStorage.getItem('pm16_patio')) || [],
            vendas: JSON.parse(localStorage.getItem('pm16_vendas')) || [],
            mensalistas: JSON.parse(localStorage.getItem('pm16_mensal')) || [],
            selos: JSON.parse(localStorage.getItem('pm16_selos')) || [],
            precos: JSON.parse(localStorage.getItem('pm16_precos')) || { 15: 6, 60: 15, 1440: 50 },
            precoMensal: JSON.parse(localStorage.getItem('pm16_precoMensal')) || 100.00,
            caixa: JSON.parse(localStorage.getItem('pm16_caixa')) || { aberto: false, saldo: 0 }
        };

        let veiculoSaindo = null;
        let chartVendas = null;

        function salvar() {
            localStorage.setItem('pm16_patio', JSON.stringify(db.patio));
            localStorage.setItem('pm16_vendas', JSON.stringify(db.vendas));
            localStorage.setItem('pm16_mensal', JSON.stringify(db.mensalistas));
            localStorage.setItem('pm16_selos', JSON.stringify(db.selos));
            localStorage.setItem('pm16_precos', JSON.stringify(db.precos));
            localStorage.setItem('pm16_precoMensal', JSON.stringify(db.precoMensal));
            localStorage.setItem('pm16_caixa', JSON.stringify(db.caixa));
        }

        // --- VALIDADOR DE CPF ---
        function validarCPF(cpf) {
            cpf = cpf.replace(/[^\d]+/g,'');
            if(cpf.length != 11 || /^(\d)\1{10}$/.test(cpf)) return false;
            let add = 0;
            for (let i=0; i < 9; i++) add += parseInt(cpf.charAt(i)) * (10 - i);
            let rev = 11 - (add % 11);
            if (rev == 10 || rev == 11) rev = 0;
            if (rev != parseInt(cpf.charAt(9))) return false;
            add = 0;
            for (let i = 0; i < 10; i++) add += parseInt(cpf.charAt(i)) * (11 - i);
            rev = 11 - (add % 11);
            if (rev == 10 || rev == 11) rev = 0;
            return rev == parseInt(cpf.charAt(10));
        }

        // --- MENSALISTAS ---
        function cadastrarMensalista() {
            const cpf = document.getElementById('mCPF').value;
            if(!validarCPF(cpf)) return alert("CPF INVÁLIDO!");

            const novo = {
                id: Date.now(),
                nome: document.getElementById('mNome').value.toUpperCase(),
                cpf: cpf.replace(/[^\d]+/g, ''),
                tel: document.getElementById('mTel').value,
                email: document.getElementById('mEmail').value,
                end: document.getElementById('mEnd').value.toUpperCase(),
                placa: document.getElementById('mPlaca').value.toUpperCase(),
                vencimento: document.getElementById('mVenc').value
            };
            db.mensalistas.push(novo); salvar(); renderMensalistas();
            alert("MENSALISTA CADASTRADO COM SUCESSO!");
            ["mNome", "mCPF", "mTel", "mEmail", "mEnd", "mPlaca", "mVenc"].forEach(id => document.getElementById(id).value = "");
        }

        function renderMensalistas() {
            document.getElementById('cardsMensalistas').innerHTML = db.mensalistas.map(m => `
                <div class="bg-white p-4 rounded-xl border shadow-sm flex justify-between items-center">
                    <div>
                        <p class="font-black text-xl italic">${m.placa}</p>
                        <p class="text-[10px] font-bold text-slate-400 uppercase">${m.nome}</p>
                        <p class="text-[9px] text-emerald-600 font-bold">VENCE: ${new Date(m.vencimento).toLocaleDateString()}</p>
                    </div>
                    <div class="flex gap-2">
                        <button onclick="imprimirCredencial(${m.id})" class="bg-slate-900 text-white p-2 rounded text-[9px] font-bold">CREDENTIAL</button>
                        <button onclick="removerMensalista(${m.id})" class="text-red-500 font-bold text-[9px]">X</button>
                    </div>
                </div>`).join('');
        }

        function imprimirCredencial(id) {
            const m = db.mensalistas.find(i => i.id === id);
            document.getElementById('ticketCorpo').innerHTML = `<h2>MENSALISTA</h2><h1 style="font-size:40px;">${m.placa}</h1><p>${m.nome}</p><p>VENCIMENTO: ${new Date(m.vencimento).toLocaleDateString()}</p>`;
            document.getElementById('qrContainer').innerHTML = ""; document.getElementById('barContainer').innerHTML = "";
            new QRCode(document.getElementById("qrContainer"), { text: m.placa, width: 128, height: 128 });
            JsBarcode("#barContainer", m.placa, { height: 40, displayValue: false });
            setTimeout(() => window.print(), 500);
        }

        // --- CONVÊNIOS / SELOS ---
        function cadastrarSelo() {
            const n = document.getElementById('sNome').value;
            const d = document.getElementById('sDesc').value;
            if(n && d) { db.selos.push({ id: Date.now(), nome: n.toUpperCase(), desc: d }); salvar(); renderSelos(); }
        }

        function renderSelos() {
            document.getElementById('listaSelos').innerHTML = db.selos.map(s => `
                <div class="bg-white p-4 rounded-xl border shadow-sm flex justify-between items-center">
                    <div><p class="font-black text-xs">${s.nome}</p><p class="text-emerald-500 font-black text-lg">${s.desc}% OFF</p></div>
                    <button onclick="imprimirSelo(${s.id})" class="bg-black text-white p-3 rounded-lg text-[10px] font-bold">TICKET</button>
                </div>`).join('');
        }

        function imprimirSelo(id) {
            const s = db.selos.find(i => i.id === id);
            document.getElementById('ticketCorpo').innerHTML = `<h3>CONVÊNIO</h3><h1>${s.nome}</h1><h2>${s.desc}% DESCONTO</h2>`;
            document.getElementById('qrContainer').innerHTML = "";
            JsBarcode("#barContainer", `SELO-${s.id}`, { height: 50 });
            setTimeout(() => window.print(), 300);
        }

        // --- OPERAÇÕES ---
        function processarFluxo() {
            if (!db.caixa.aberto) return alert("Abra o caixa!");
            const input = document.getElementById('inputPrincipal').value.toUpperCase().trim();
            if (!input) return;

            // Se for leitura de selo/convênio
            if(input.startsWith("SELO-")) {
                const s = db.selos.find(i => i.id == input.replace("SELO-",""));
                if(s && veiculoSaindo) {
                    let v = parseFloat(document.getElementById('outValor').innerText.replace('R$ ',''));
                    v = v * (1 - (s.desc/100));
                    document.getElementById('outValor').innerText = "R$ " + v.toFixed(2);
                    calcularTroco(); alert("DESCONTO APLICADO!");
                }
                document.getElementById('inputPrincipal').value = ''; return;
            }

            const v = db.patio.find(i => i.placa === input);
            if (v) prepararSaida(v); else entrada(input);
            document.getElementById('inputPrincipal').value = '';
        }

        function entrada(placa) {
            const novo = { id: Date.now(), placa, entrada: new Date().toISOString() };
            db.patio.push(novo); salvar(); renderPatio(); imprimirRecibo("ENTRADA", novo);
        }

        function prepararSaida(v) {
            veiculoSaindo = v;
            const agora = new Date();
            const minutos = Math.max(1, Math.ceil(Math.abs(agora - new Date(v.entrada)) / 60000));
            const faixas = Object.keys(db.precos).map(Number).sort((a, b) => a - b);
            let valor = db.precos[faixas[faixas.length - 1]];
            for (let f of faixas) { if (minutos <= f) { valor = db.precos[f]; break; } }
            
            const mensa = db.mensalistas.find(m => m.placa === v.placa);
            const badge = document.getElementById('badgeStatus');
            const btnI = document.getElementById('btnIsentar');

            if(mensa) {
                const vencido = new Date(mensa.vencimento) < agora;
                badge.innerText = vencido ? "VENCIDO" : "MENSALISTA";
                badge.className = `text-[9px] px-2 py-1 rounded font-bold ${vencido ? 'bg-red-500' : 'bg-emerald-500 text-black'}`;
                if(!vencido) { valor = 0; btnI.classList.remove('hidden'); } else { btnI.classList.add('hidden'); }
            } else {
                badge.innerText = ""; btnI.classList.add('hidden');
            }

            document.getElementById('outPlaca').innerText = v.placa;
            document.getElementById('outTempo').innerText = minutos + " MINUTOS";
            document.getElementById('outValor').innerText = "R$ " + valor.toFixed(2);
            document.getElementById('painelSaida').classList.remove('hidden');
        }

        function finalizar(metodo) {
            let valor = parseFloat(document.getElementById('outValor').innerText.replace('R$ ', ''));
            if(metodo === 'MENSALISTA') valor = 0;
            db.vendas.push({ data: new Date().toISOString(), valor, metodo, placa: veiculoSaindo.placa });
            if(metodo === 'DINHEIRO') db.caixa.saldo += valor;
            db.patio = db.patio.filter(v => v.id !== veiculoSaindo.id);
            salvar(); renderPatio(); renderCaixa(); imprimirRecibo("SAIDA", {placa: veiculoSaindo.placa, valor, metodo});
            cancelarSaida();
        }

        // --- TARIFAS E PRO RATA ---
        function salvarTabelaMensal() {
            db.precoMensal = parseFloat(document.getElementById('precoMensalInput').value);
            salvar(); alert("TABELA SALVA!");
        }

        function gerarTabelaReferencia() {
            const v = parseFloat(document.getElementById('precoMensalInput').value) || 0;
            const container = document.getElementById('tabelaProRataFisica');
            container.innerHTML = '';
            for (let i = 1; i <= 30; i++) {
                container.innerHTML += `<div class="cell-pro-rata"><div class="cell-label">${i}d</div><div class="cell-value">R$ ${(v/30*i).toFixed(2)}</div></div>`;
            }
        }

        function renderTarifas() {
            const sorted = Object.keys(db.precos).map(Number).sort((a,b) => a-b);
            document.getElementById('tarifarioContainer').innerHTML = sorted.map(m => `
                <div class="bg-slate-50 p-2 border rounded-xl text-center relative group">
                    <label class="text-[8px] font-bold text-slate-400">ATÉ ${m} MIN</label>
                    <input onchange="db.precos[${m}]=parseFloat(this.value);salvar()" type="number" class="bg-transparent font-black w-full text-center text-xs outline-none" value="${db.precos[m]}">
                </div>`).join('');
        }

        function adicionarFracao() {
            const m = prompt("Minutos:"); const v = prompt("Valor R$:");
            if(m && v) { db.precos[parseInt(m)] = parseFloat(v); salvar(); renderTarifas(); }
        }

        // --- AUXILIARES ---
        function renderPatio() {
            document.getElementById('gridPatio').innerHTML = db.patio.map(v => `<div onclick='prepararSaida(${JSON.stringify(v)})' class="bg-white border p-5 rounded-2xl hover:border-emerald-500 cursor-pointer text-center shadow-sm"><p class="font-black italic text-lg">${v.placa}</p><p class="text-[9px] text-slate-400">${new Date(v.entrada).toLocaleTimeString([],{hour:'2-digit',minute:'2-digit'})}</p></div>`).join('');
        }

        function calcularTroco() {
            const t = parseFloat(document.getElementById('outValor').innerText.replace('R$ ', ''));
            const p = parseFloat(document.getElementById('valorRecebido').value) || 0;
            document.getElementById('displayTroco').innerText = `TROCO: R$ ${(p-t).toFixed(2)}`;
        }

        function abrirFecharCaixa() {
            if(!db.caixa.aberto) { db.caixa.aberto = true; db.caixa.saldo = parseFloat(prompt("Fundo Inicial:", "0") || 0); }
            else { if(confirm("Fechar caixa?")) db.caixa.aberto = false; }
            salvar(); renderCaixa();
        }

        function renderCaixa() {
            document.getElementById('valorEmCaixa').innerText = `R$ ${db.caixa.saldo.toFixed(2)}`;
            document.getElementById('btnCaixa').innerText = db.caixa.aberto ? "Fechar Turno" : "Abrir Turno";
        }

        function imprimirRecibo(tipo, dados) {
            document.getElementById('ticketCorpo').innerHTML = `<h2>${tipo}</h2><h1>${dados.placa}</h1><p>${new Date().toLocaleString()}</p>${dados.valor ? `<h3>VALOR: R$ ${dados.valor.toFixed(2)}</h3>` : ''}`;
            document.getElementById('qrContainer').innerHTML = ""; document.getElementById('barContainer').innerHTML = "";
            if(tipo === "ENTRADA") JsBarcode("#barContainer", dados.placa, { height: 40 });
            setTimeout(() => window.print(), 300);
        }

        function changeTab(id) {
            document.querySelectorAll('.tab-content').forEach(t => t.classList.remove('active'));
            document.getElementById('tab-' + id).classList.add('active');
            document.querySelectorAll('.tab-btn').forEach(b => { b.classList.remove('bg-emerald-500', 'text-white'); b.classList.add('text-slate-500'); });
            event.currentTarget.classList.add('bg-emerald-500', 'text-white');
        }

        function popularFiltroAno() {
            const s = document.getElementById('filtroAno');
            for(let i = 2024; i <= new Date().getFullYear(); i++) {
                const o = document.createElement('option'); o.value = i; o.innerText = `ANO ${i}`; s.appendChild(o);
            }
            atualizarRelatorios();
        }

        function atualizarRelatorios() {
            const ano = parseInt(document.getElementById('filtroAno').value);
            const meses = new Array(12).fill(0);
            db.vendas.forEach(v => { if(new Date(v.data).getFullYear() === ano) meses[new Date(v.data).getMonth()] += v.valor; });
            const ctx = document.getElementById('graficoVendas').getContext('2d');
            if (chartVendas) chartVendas.destroy();
            chartVendas = new Chart(ctx, { type: 'bar', data: { labels: ["Jan","Fev","Mar","Abr","Mai","Jun","Jul","Ago","Set","Out","Nov","Dez"], datasets: [{ label: 'R$', data: meses, backgroundColor: '#10b981' }] }, options: { maintainAspectRatio: false } });
        }

        function exportarExcel() {
            let csv = "Data;Placa;Metodo;Valor\n";
            db.vendas.forEach(v => { csv += `${new Date(v.data).toLocaleString()};${v.placa};${v.metodo};${v.valor}\n`; });
            const link = document.createElement("a");
            link.href = URL.createObjectURL(new Blob([csv], { type: 'text/csv' }));
            link.download = `Relatorio_ParkMaster.csv`; link.click();
        }

        function removerMensalista(id) { if(confirm("Excluir?")) { db.mensalistas = db.mensalistas.filter(m => m.id !== id); salvar(); renderMensalistas(); } }
        function cancelarSaida() { document.getElementById('painelSaida').classList.add('hidden'); }

        setInterval(() => { document.getElementById('relogio').innerText = new Date().toLocaleTimeString(); }, 1000);
        
        // INIT
        document.getElementById('precoMensalInput').value = db.precoMensal;
        renderTarifas(); gerarTabelaReferencia(); renderPatio(); renderCaixa(); renderMensalistas(); renderSelos(); popularFiltroAno();
    </script>
</body>
</html>
