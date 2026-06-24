MARIGESTAO 
<!DOCTYPE html>
<html lang="pt-BR" class="h-full bg-slate-50">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fluxo de Caixa & Fechamento Inteligente</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome para Ícones -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94a3b8;
        }
    </style>
</head>
<body class="h-full text-slate-800 antialiased font-sans flex flex-col">

    <!-- Notificação Flutuante (Toast) -->
    <div id="toast" class="fixed top-5 right-5 z-50 transform translate-y-[-150%] transition-transform duration-300 ease-out flex items-center p-4 mb-4 w-full max-w-xs text-gray-500 bg-white rounded-xl shadow-lg border border-slate-100" role="alert">
        <div id="toast-icon-container" class="inline-flex flex-shrink-0 justify-center items-center w-8 h-8 rounded-lg">
            <i id="toast-icon" class="fa-solid"></i>
        </div>
        <div id="toast-message" class="ml-3 text-sm font-semibold text-slate-700"></div>
    </div>

    <!-- Modal de Confirmação Customizado -->
    <div id="confirm-modal" class="fixed inset-0 z-50 hidden items-center justify-center bg-black/50 backdrop-blur-sm p-4">
        <div class="bg-white rounded-2xl max-w-md w-full p-6 shadow-2xl border border-slate-100 transform scale-95 transition-all">
            <div class="text-center">
                <div class="mx-auto flex items-center justify-center h-12 w-12 rounded-full bg-red-100 text-red-600 mb-4">
                    <i class="fa-solid fa-triangle-exclamation text-lg"></i>
                </div>
                <h3 class="text-lg font-bold text-slate-950" id="confirm-title">Excluir Item?</h3>
                <p class="text-sm text-slate-500 mt-2" id="confirm-body">Esta ação não pode ser desfeita. Tem certeza que deseja continuar?</p>
            </div>
            <div class="flex gap-3 mt-6">
                <button onclick="closeConfirmModal(false)" class="flex-1 py-2.5 px-4 bg-slate-100 hover:bg-slate-200 text-slate-700 font-semibold rounded-xl text-sm transition">Cancelar</button>
                <button id="confirm-yes-btn" class="flex-1 py-2.5 px-4 bg-red-600 hover:bg-red-700 text-white font-semibold rounded-xl text-sm transition">Confirmar</button>
            </div>
        </div>
    </div>

    <div class="min-h-screen flex flex-col">
        <!-- Header -->
        <header class="bg-white border-b border-slate-200 sticky top-0 z-30">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex items-center justify-between h-16">
                    <div class="flex items-center gap-3">
                        <div class="bg-blue-600 text-white p-2.5 rounded-xl shadow-md shadow-blue-200">
                            <i class="fa-solid fa-wallet text-xl"></i>
                        </div>
                        <div>
                            <h1 class="text-lg font-bold text-slate-900 leading-tight">Mariane Gestão de Dados</h1>
                            <p class="text-xs text-slate-500">Auditoria Automatizada, Packs & Fechamento de Caixa</p>
                        </div>
                    </div>
                    <!-- Status do Firebase -->
                    <div class="flex items-center gap-3">
                        <div id="firebase-status" class="flex items-center gap-1.5 py-1.5 px-3 rounded-lg text-xs font-semibold bg-amber-50 text-amber-700 border border-amber-200">
                            <i class="fa-solid fa-circle-notch animate-spin"></i>
                            <span>Conectando...</span>
                        </div>
                        <!-- Indicador de Data Atual -->
                        <div class="flex items-center gap-2 bg-slate-100 py-1.5 px-3 rounded-lg text-xs font-semibold text-slate-600">
                            <i class="fa-solid fa-calendar"></i>
                            <span id="current-date-header">--/--/----</span>
                        </div>
                    </div>
                </div>
            </div>
        </header>

        <!-- Container Principal -->
        <main class="flex-1 max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-6">
            <!-- Abas de Navegação -->
            <div class="flex border-b border-slate-200 mb-6 overflow-x-auto gap-2">
                <button onclick="switchTab('dashboard-tab')" id="btn-dashboard-tab" class="tab-btn py-3 px-4 font-semibold text-sm border-b-2 border-blue-600 text-blue-600 flex items-center gap-2 whitespace-nowrap transition-all">
                    <i class="fa-solid fa-chart-line"></i> Painel Geral
                </button>
                <button onclick="switchTab('leitor-tab')" id="btn-leitor-tab" class="tab-btn py-3 px-4 font-semibold text-sm border-b-2 border-transparent text-slate-500 hover:text-slate-800 flex items-center gap-2 whitespace-nowrap transition-all">
                    <i class="fa-solid fa-wand-magic-sparkles text-purple-600"></i> Leitor Automatizado
                </button>
                <button onclick="switchTab('lancamentos-tab')" id="btn-lancamentos-tab" class="tab-btn py-3 px-4 font-semibold text-sm border-b-2 border-transparent text-slate-500 hover:text-slate-800 flex items-center gap-2 whitespace-nowrap transition-all">
                    <i class="fa-solid fa-cash-register"></i> Novo Fechamento <span id="edit-indicator" class="hidden bg-amber-500 text-white text-[9px] px-1.5 py-0.5 rounded-full font-bold ml-1">Editando</span>
                </button>
                <button onclick="switchTab('retiradas-tab')" id="btn-retiradas-tab" class="tab-btn py-3 px-4 font-semibold text-sm border-b-2 border-transparent text-slate-500 hover:text-slate-800 flex items-center gap-2 whitespace-nowrap transition-all">
                    <i class="fa-solid fa-hand-holding-dollar text-red-600"></i> Retiradas
                </button>
                <button onclick="switchTab('fiados-tab')" id="btn-fiados-tab" class="tab-btn py-3 px-4 font-semibold text-sm border-b-2 border-transparent text-slate-500 hover:text-slate-800 flex items-center gap-2 whitespace-nowrap transition-all">
                    <i class="fa-solid fa-user-tag"></i> Controle de Fiados
                </button>
                <button onclick="switchTab('historico-tab')" id="btn-historico-tab" class="tab-btn py-3 px-4 font-semibold text-sm border-b-2 border-transparent text-slate-500 hover:text-slate-800 flex items-center gap-2 whitespace-nowrap transition-all">
                    <i class="fa-solid fa-clock-rotate-left"></i> Histórico Detalhado
                </button>
            </div>

            <!-- CONTEÚDO DAS ABAS -->

            <!-- Aba 1: Dashboard -->
            <div id="dashboard-tab" class="tab-content block space-y-6">
                <!-- Filtros Dashboard Rápido -->
                <div class="bg-white p-4 rounded-2xl border border-slate-200 flex flex-wrap items-center justify-between gap-4">
                    <div class="flex items-center gap-3">
                        <span class="text-sm font-semibold text-slate-500">Visualizar período:</span>
                        <div class="inline-flex rounded-lg bg-slate-100 p-0.5">
                            <button onclick="setDashboardPeriod('hoje')" id="dash-p-hoje" class="dash-period-btn px-3 py-1.5 rounded-md text-xs font-semibold bg-white text-slate-800 shadow-sm transition">Hoje</button>
                            <button onclick="setDashboardPeriod('mes')" id="dash-p-mes" class="dash-period-btn px-3 py-1.5 rounded-md text-xs font-semibold text-slate-500 hover:text-slate-800 transition">Este Mês</button>
                            <button onclick="setDashboardPeriod('todos')" id="dash-p-todos" class="dash-period-btn px-3 py-1.5 rounded-md text-xs font-semibold text-slate-500 hover:text-slate-800 transition">Tudo</button>
                        </div>
                    </div>
                    <div class="text-xs text-slate-400 italic" id="dash-periodo-desc">Mostrando dados de hoje</div>
                </div>

                <!-- Cards de Indicadores Principais -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-4">
                    <!-- Dinheiro Físico em Caixa -->
                    <div class="bg-white p-5 rounded-2xl border border-slate-200 flex flex-col justify-between shadow-sm relative overflow-hidden">
                        <div class="absolute right-3 top-3 text-red-500/10 text-4xl font-black"><i class="fa-solid fa-money-bill-wave"></i></div>
                        <div>
                            <span class="text-xs font-semibold text-slate-400 uppercase tracking-wider">Dinheiro Físico</span>
                            <h3 class="text-xl font-bold text-slate-900 mt-1" id="dash-val-dinheiro">R$ 0,00</h3>
                        </div>
                        <div class="mt-3 pt-3 border-t border-slate-100 text-xs flex justify-between items-center">
                            <span class="text-slate-500">Diferença:</span>
                            <span id="dash-dif-dinheiro" class="font-bold">R$ 0,00</span>
                        </div>
                    </div>
                    <!-- Pix Físico -->
                    <div class="bg-white p-5 rounded-2xl border border-slate-200 flex flex-col justify-between shadow-sm relative overflow-hidden">
                        <div class="absolute right-3 top-3 text-sky-500/10 text-4xl font-black"><i class="fa-brands fa-pix"></i></div>
                        <div>
                            <span class="text-xs font-semibold text-slate-400 uppercase tracking-wider">Pix Físico (Conta)</span>
                            <h3 class="text-xl font-bold text-slate-900 mt-1" id="dash-val-pix">R$ 0,00</h3>
                        </div>
                        <div class="mt-3 pt-3 border-t border-slate-100 text-xs flex justify-between items-center">
                            <span class="text-slate-500">Diferença:</span>
                            <span id="dash-dif-pix" class="font-bold">R$ 0,00</span>
                        </div>
                    </div>
                    <!-- Cartões (Máquina) -->
                    <div class="bg-white p-5 rounded-2xl border border-slate-200 flex flex-col justify-between shadow-sm relative overflow-hidden">
                        <div class="absolute right-3 top-3 text-amber-500/10 text-4xl font-black"><i class="fa-solid fa-credit-card"></i></div>
                        <div>
                            <span class="text-xs font-semibold text-slate-400 uppercase tracking-wider">Valor nas Máquinas</span>
                            <h3 class="text-xl font-bold text-slate-900 mt-1" id="dash-val-cartao">R$ 0,00</h3>
                        </div>
                        <div class="mt-3 pt-3 border-t border-slate-100 text-xs flex justify-between items-center">
                            <span class="text-slate-500">Crédito/Débito:</span>
                            <span id="dash-cartao-split-summary" class="font-bold text-slate-600">R$ 0 / R$ 0</span>
                        </div>
                    </div>
                    <!-- Total Retiradas -->
                    <div class="bg-white p-5 rounded-2xl border border-slate-200 flex flex-col justify-between shadow-sm relative overflow-hidden border-l-red-500 border-l-4">
                        <div class="absolute right-3 top-3 text-red-500/10 text-4xl font-black"><i class="fa-solid fa-hand-holding-dollar"></i></div>
                        <div>
                            <span class="text-xs font-semibold text-red-500 uppercase tracking-wider">Total Retiradas</span>
                            <h3 class="text-xl font-bold text-red-700 mt-1" id="dash-val-retiradas">R$ 0,00</h3>
                        </div>
                        <div class="mt-3 pt-3 border-t border-slate-100 text-xs flex justify-between items-center">
                            <span class="text-slate-500">Sangrias/Saídas:</span>
                            <span id="dash-retiradas-split-summary" class="font-bold text-slate-600">R$ 0 / R$ 0</span>
                        </div>
                    </div>
                    <!-- Total Real Geral -->
                    <div class="bg-blue-600 p-5 rounded-2xl text-white flex flex-col justify-between shadow-lg shadow-blue-100 relative overflow-hidden">
                        <div class="absolute right-2 top-2 text-white/5 text-5xl font-black"><i class="fa-solid fa-vault"></i></div>
                        <div>
                            <span class="text-xs font-semibold text-blue-200 uppercase tracking-wider">Balanço Final Físico</span>
                            <h3 class="text-2xl font-black mt-1" id="dash-val-total">R$ 0,00</h3>
                        </div>
                        <div class="mt-3 pt-3 border-t border-blue-500 text-xs flex justify-between items-center">
                            <span class="text-blue-200">Diferença Geral:</span>
                            <span id="dash-balanco-final" class="font-bold text-white">R$ 0,00</span>
                        </div>
                    </div>
                </div>

                <!-- Outros Cards Adicionais (Fiados) -->
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div class="bg-white p-4 rounded-xl border border-slate-200 flex items-center justify-between">
                        <div>
                            <span class="text-xs font-semibold text-slate-400 uppercase">Fiados Pendentes</span>
                            <h4 class="text-lg font-bold text-orange-600 mt-0.5" id="dash-val-fiado">R$ 0,00</h4>
                        </div>
                        <div class="text-right">
                            <span class="text-xs text-slate-400 block">Clientes</span>
                            <span class="text-sm font-bold text-slate-700" id="dash-fiados-ativos-count">0</span>
                        </div>
                    </div>
                    <div class="bg-white p-4 rounded-xl border border-slate-200 flex items-center justify-between">
                        <div>
                            <span class="text-xs font-semibold text-slate-400 uppercase">Status Geral do Dia</span>
                            <h4 class="text-sm font-bold text-slate-700 mt-1 flex items-center gap-1.5">
                                <i class="fa-solid fa-circle-check text-emerald-500"></i> Caixa Operacional
                            </h4>
                        </div>
                    </div>
                </div>

                <!-- Comparativos e Gráficos de Controle -->
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                    <!-- Detalhamento Comparativo -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 lg:col-span-2 space-y-4">
                        <div class="flex items-center justify-between border-b border-slate-100 pb-3">
                            <h2 class="font-bold text-slate-900 flex items-center gap-2"><i class="fa-solid fa-balance-scale text-blue-600"></i> Auditoria de Caixa (Sistema x Contagem)</h2>
                            <span class="text-xs text-slate-400">Análise do Período</span>
                        </div>

                        <!-- Dinheiro -->
                        <div>
                            <div class="flex justify-between text-xs font-semibold text-slate-500 mb-1">
                                <span>Dinheiro</span>
                                <span>Sistema: <span id="bar-dinheiro-sis">R$ 0</span> | Contado: <span id="bar-dinheiro-fis">R$ 0</span></span>
                            </div>
                            <div class="w-full bg-slate-100 rounded-full h-3 overflow-hidden flex">
                                <div id="bar-dinheiro-sis-fill" class="bg-red-300 h-full rounded-l" style="width: 0%"></div>
                                <div id="bar-dinheiro-fis-fill" class="bg-red-500 h-full rounded-r border-l border-white" style="width: 0%"></div>
                            </div>
                        </div>

                        <!-- Pix -->
                        <div>
                            <div class="flex justify-between text-xs font-semibold text-slate-500 mb-1">
                                <span>Pix</span>
                                <span>Sistema: <span id="bar-pix-sis">R$ 0</span> | Contado: <span id="bar-pix-fis">R$ 0</span></span>
                            </div>
                            <div class="w-full bg-slate-100 rounded-full h-3 overflow-hidden flex">
                                <div id="bar-pix-sis-fill" class="bg-sky-300 h-full rounded-l" style="width: 0%"></div>
                                <div id="bar-pix-fis-fill" class="bg-sky-500 h-full rounded-r border-l border-white" style="width: 0%"></div>
                            </div>
                        </div>

                        <!-- Crédito -->
                        <div>
                            <div class="flex justify-between text-xs font-semibold text-slate-500 mb-1">
                                <span>Cartão de Crédito</span>
                                <span>Sistema: <span id="bar-credito-sis">R$ 0</span> | Máquina: <span id="bar-credito-fis">R$ 0</span></span>
                            </div>
                            <div class="w-full bg-slate-100 rounded-full h-3 overflow-hidden flex">
                                <div id="bar-credito-sis-fill" class="bg-amber-200 h-full rounded-l" style="width: 0%"></div>
                                <div id="bar-credito-fis-fill" class="bg-amber-400 h-full rounded-r border-l border-white" style="width: 0%"></div>
                            </div>
                        </div>

                        <!-- Débito -->
                        <div>
                            <div class="flex justify-between text-xs font-semibold text-slate-500 mb-1">
                                <span>Cartão de Débito</span>
                                <span>Sistema: <span id="bar-debito-sis">R$ 0</span> | Máquina: <span id="bar-debito-fis">R$ 0</span></span>
                            </div>
                            <div class="w-full bg-slate-100 rounded-full h-3 overflow-hidden flex">
                                <div id="bar-debito-sis-fill" class="bg-yellow-300 h-full rounded-l" style="width: 0%"></div>
                                <div id="bar-debito-fis-fill" class="bg-yellow-500 h-full rounded-r border-l border-white" style="width: 0%"></div>
                            </div>
                        </div>
                    </div>

                    <!-- Controle de Saídas / Sangria no Período -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between border-b border-slate-100 pb-3 mb-4">
                                <h2 class="font-bold text-slate-900 flex items-center gap-2"><i class="fa-solid fa-receipt text-red-500"></i> Despesas do Período</h2>
                            </div>
                            <div class="space-y-3 text-sm">
                                <div class="flex justify-between items-center p-2.5 bg-slate-50 rounded-lg">
                                    <span class="text-slate-600 font-medium">Taxas de Máquina</span>
                                    <span class="font-bold text-slate-800" id="desp-taxas">R$ 0,00</span>
                                </div>
                                <div class="flex justify-between items-center p-2.5 bg-slate-50 rounded-lg">
                                    <span class="text-slate-600 font-medium">Sangria de Caixa</span>
                                    <span class="font-bold text-slate-800" id="desp-sangria">R$ 0,00</span>
                                </div>
                                <div class="flex justify-between items-center p-2.5 bg-slate-50 rounded-lg">
                                    <span class="text-slate-600 font-medium">Saídas do Dia</span>
                                    <span class="font-bold text-slate-800" id="desp-saidas">R$ 0,00</span>
                                </div>
                                <div class="flex justify-between items-center p-2.5 bg-slate-50 rounded-lg">
                                    <span class="text-slate-600 font-medium">Outros Desvios</span>
                                    <span class="font-bold text-slate-800" id="desp-outros">R$ 0,00</span>
                                </div>
                            </div>
                        </div>
                        <div class="mt-6 pt-4 border-t border-slate-100 flex items-center justify-between text-[11px] text-slate-400">
                            <span>Soma das retiradas no intervalo.</span>
                            <button onclick="limparTudo()" class="text-rose-500 hover:text-rose-700 font-bold transition flex items-center gap-1"><i class="fa-solid fa-trash-can"></i> Limpar Tudo</button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Aba 2: Leitor de Relatórios -->
            <div id="leitor-tab" class="tab-content hidden space-y-6">
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                    <!-- Entrada do Relatório em Texto -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col space-y-4">
                        <div>
                            <h2 class="font-bold text-slate-900 text-base flex items-center gap-2"><i class="fa-solid fa-wand-magic-sparkles text-purple-600"></i> Auditor Inteligente de Caixa</h2>
                            <p class="text-xs text-slate-400 mt-0.5">Cole o relatório bruto do seu PDV. O sistema fará a auditoria contábil completa separando automaticamente Packs de Unidades.</p>
                        </div>
                        <textarea id="raw-report-text" rows="14" placeholder="Cole aqui o relatório de vendas diário do PDV..." class="w-full bg-slate-50 border border-slate-200 hover:border-slate-300 focus:border-purple-500 focus:bg-white rounded-xl p-3.5 text-xs font-mono text-slate-700 transition outline-none resize-none"></textarea>
                        
                        <div class="flex gap-2">
                            <button onclick="processarRelatorioTexto()" class="flex-1 py-2.5 bg-purple-600 hover:bg-purple-700 text-white font-bold rounded-xl text-xs transition-all shadow-md shadow-purple-100 flex items-center justify-center gap-2">
                                <i class="fa-solid fa-wand-magic"></i> Processar & Auditar
                            </button>
                            <button onclick="limparLeitor()" class="py-2.5 px-4 bg-slate-100 hover:bg-slate-200 text-slate-600 font-semibold rounded-xl text-xs transition-all">
                                Limpar
                            </button>
                        </div>
                    </div>

                    <!-- Resultados da Leitura -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm lg:col-span-2 flex flex-col space-y-6">
                        <div class="flex items-center justify-between border-b border-slate-100 pb-4">
                            <div>
                                <h2 class="font-bold text-slate-900 text-base flex items-center gap-2"><i class="fa-solid fa-magnifying-glass-chart text-purple-600"></i> Auditoria de Estoque e Vendas</h2>
                                <p class="text-xs text-slate-400">Packs de 12 e vendas avulsas divididos e calculados de forma automática</p>
                            </div>
                            <button id="btn-aplicar-fechamento" onclick="aplicarAoFechamento()" disabled class="py-2 px-3.5 bg-slate-100 text-slate-400 font-bold rounded-xl text-xs transition-all flex items-center gap-1.5 cursor-not-allowed">
                                <i class="fa-solid fa-share-from-square"></i> Aplicar ao Fechamento
                            </button>
                        </div>

                        <!-- Cards Estatísticos do Leitor -->
                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                            <div class="bg-purple-50 p-4 rounded-xl border border-purple-100">
                                <span class="text-[10px] font-bold text-purple-500 uppercase tracking-wider block">Faturamento Calculado</span>
                                <span class="text-lg font-extrabold text-purple-950 block mt-1" id="leitor-total-fat">R$ 0,00</span>
                            </div>
                            <div class="bg-blue-50 p-4 rounded-xl border border-blue-100">
                                <span class="text-[10px] font-bold text-blue-500 uppercase tracking-wider block">Estoque Físico de Saída</span>
                                <span class="text-lg font-extrabold text-blue-950 block mt-1" id="leitor-total-itens">0 un.</span>
                            </div>
                            <div class="bg-emerald-50 p-4 rounded-xl border border-emerald-100">
                                <span class="text-[10px] font-bold text-emerald-500 uppercase tracking-wider block">Mix de Produtos</span>
                                <span class="text-lg font-extrabold text-emerald-950 block mt-1" id="leitor-produtos-distintos">0 cadastros</span>
                            </div>
                        </div>

                        <!-- Formas de Pagamento Mapeadas -->
                        <div class="space-y-3">
                            <h3 class="text-xs font-bold text-slate-400 uppercase tracking-wider flex items-center gap-1.5"><i class="fa-solid fa-credit-card"></i> Divisão Inteligente por Meios de Pagamento</h3>
                            <div class="grid grid-cols-2 sm:grid-cols-5 gap-2">
                                <div class="p-2.5 bg-slate-50 rounded-lg border border-slate-100 text-center">
                                    <span class="block text-[10px] text-slate-400 font-bold uppercase">Dinheiro</span>
                                    <span class="text-xs font-bold text-slate-800 animate-pulse" id="leitor-meio-dinheiro">R$ 0,00</span>
                                </div>
                                <div class="p-2.5 bg-slate-50 rounded-lg border border-slate-100 text-center">
                                    <span class="block text-[10px] text-slate-400 font-bold uppercase">Pix</span>
                                    <span class="text-xs font-bold text-slate-800" id="leitor-meio-pix">R$ 0,00</span>
                                </div>
                                <div class="p-2.5 bg-slate-50 rounded-lg border border-slate-100 text-center">
                                    <span class="block text-[10px] text-slate-400 font-bold uppercase">Crédito</span>
                                    <span class="text-xs font-bold text-slate-800" id="leitor-meio-credito">R$ 0,00</span>
                                </div>
                                <div class="p-2.5 bg-slate-50 rounded-lg border border-slate-100 text-center">
                                    <span class="block text-[10px] text-slate-400 font-bold uppercase">Débito</span>
                                    <span class="text-xs font-bold text-slate-800" id="leitor-meio-debito">R$ 0,00</span>
                                </div>
                                <div class="p-2.5 bg-slate-50 rounded-lg border border-slate-100 text-center">
                                    <span class="block text-[10px] text-slate-400 font-bold uppercase">Fiado</span>
                                    <span class="text-xs font-bold text-slate-800" id="leitor-meio-fiado">R$ 0,00</span>
                                </div>
                            </div>
                            <span class="text-[10px] text-slate-400 block italic leading-none">* Valores de vendas combinadas (ex: Dinheiro+Pix) foram rateados perfeitamente em 50% para cada caixa.</span>
                        </div>

                        <!-- Tabela de Produtos Extraídos -->
                        <div class="flex-1 min-h-[200px] flex flex-col">
                            <h3 class="text-xs font-bold text-slate-400 uppercase tracking-wider mb-2"><i class="fa-solid fa-boxes-stacked"></i> Inventário Físico Consolidado (Auditoria de Saída de Estoque)</h3>
                            <div class="overflow-x-auto border border-slate-150 rounded-xl max-h-[300px] overflow-y-auto">
                                <table class="w-full text-left text-xs">
                                    <thead class="bg-slate-50 sticky top-0 border-b border-slate-100">
                                        <tr class="text-slate-500 font-bold">
                                            <th class="p-3">Item / Descrição</th>
                                            <th class="p-3">Tipo de Saída</th>
                                            <th class="p-3 text-center">Quantidade Real (Unidades)</th>
                                            <th class="p-3 text-right">Valor Praticado (Média)</th>
                                            <th class="p-3 text-right">Faturamento Total</th>
                                        </tr>
                                    </thead>
                                    <tbody id="tabela-leitor-corpo" class="divide-y divide-slate-100">
                                        <tr>
                                            <td colspan="5" class="p-8 text-center text-slate-400 italic">Insira e processe o texto para analisar as vendas do dia.</td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Aba 3: Novo Fechamento -->
            <div id="lancamentos-tab" class="tab-content hidden max-w-4xl mx-auto">
                <form id="form-fechamento" onsubmit="salvarFechamento(event)" class="space-y-6">
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col sm:flex-row sm:items-center justify-between gap-4">
                        <div>
                            <h2 class="font-bold text-slate-900 text-lg flex items-center gap-2"><i class="fa-solid fa-calendar-day text-blue-600"></i> Informações do Caixa</h2>
                            <p class="text-xs text-slate-400 mt-0.5">Selecione a data correspondente para efetuar o fechamento</p>
                        </div>
                        <div class="form-group w-full sm:max-w-xs">
                            <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider mb-1 block">Data do Movimento</label>
                            <input type="date" id="data-movimento" class="w-full bg-slate-50 border border-slate-200 focus:border-blue-500 focus:bg-white rounded-xl py-2 px-3.5 text-sm font-semibold outline-none transition" required>
                        </div>
                    </div>

                    <!-- Formulários de Valores de Entrada -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm space-y-6">
                        <div class="border-b border-slate-100 pb-4">
                            <h2 class="font-bold text-slate-900 text-lg flex items-center gap-2"><i class="fa-solid fa-vault text-blue-600"></i> Valores e Contagens de Caixa</h2>
                            <p class="text-xs text-slate-400 mt-0.5">Informe os valores gerados pelo sistema e compare com o que foi coletado em caixa.</p>
                        </div>

                        <!-- Linha: Dinheiro -->
                        <div class="p-5 rounded-2xl bg-red-50/40 border border-red-100/50 space-y-4">
                            <div class="flex items-center justify-between border-b border-red-100/50 pb-2">
                                <h3 class="text-sm font-bold text-red-800 flex items-center gap-2"><i class="fa-solid fa-money-bill-wave"></i> Dinheiro Físico</h3>
                                <span class="text-[11px] text-red-600 font-semibold bg-red-100/40 px-2.5 py-0.5 rounded-full">Espécie em Gaveta</span>
                            </div>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                <div class="form-group">
                                    <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valores do Sistema (R$)</label>
                                    <input type="number" step="0.01" id="dinheiro-sistema" placeholder="0,00" class="w-full bg-white border border-slate-200 focus:border-blue-500 rounded-lg py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                                </div>
                                <div class="form-group">
                                    <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valores Físicos (R$)</label>
                                    <input type="number" step="0.01" id="dinheiro-fisico" placeholder="0,00" class="w-full bg-white border border-slate-200 focus:border-blue-500 rounded-lg py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                                </div>
                            </div>
                        </div>

                        <!-- Linha: Pix -->
                        <div class="p-5 rounded-2xl bg-sky-50/40 border border-sky-100/50 space-y-4">
                            <div class="flex items-center justify-between border-b border-sky-100/50 pb-2">
                                <h3 class="text-sm font-bold text-sky-800 flex items-center gap-2"><i class="fa-brands fa-pix"></i> Pix / Transferências</h3>
                                <span class="text-[11px] text-sky-600 font-semibold bg-sky-100/40 px-2.5 py-0.5 rounded-full">Conta Bancária</span>
                            </div>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                <div class="form-group">
                                    <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valores do Sistema (R$)</label>
                                    <input type="number" step="0.01" id="pix-sistema" placeholder="0,00" class="w-full bg-white border border-slate-200 focus:border-blue-500 rounded-lg py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                                </div>
                                <div class="form-group">
                                    <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valores Físicos (R$)</label>
                                    <input type="number" step="0.01" id="pix-fisico" placeholder="0,00" class="w-full bg-white border border-slate-200 focus:border-blue-500 rounded-lg py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                                </div>
                            </div>
                        </div>

                        <!-- Linha: Crédito -->
                        <div class="p-5 rounded-2xl bg-amber-50/40 border border-amber-100/50 space-y-4">
                            <div class="flex items-center justify-between border-b border-amber-100/50 pb-2">
                                <h3 class="text-sm font-bold text-amber-800 flex items-center gap-2"><i class="fa-solid fa-credit-card"></i> Cartão de Crédito</h3>
                                <span class="text-[11px] text-amber-600 font-semibold bg-amber-100/40 px-2.5 py-0.5 rounded-full">Lançamento de Crédito</span>
                            </div>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                <div class="form-group">
                                    <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valores do Sistema (R$)</label>
                                    <input type="number" step="0.01" id="credito-sistema" placeholder="0,00" class="w-full bg-white border border-slate-200 focus:border-blue-500 rounded-lg py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                                </div>
                                <div class="form-group">
                                    <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valores na Máquina (R$)</label>
                                    <input type="number" step="0.01" id="credito-fisico" placeholder="0,00" class="w-full bg-white border border-slate-200 focus:border-blue-500 rounded-lg py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                                </div>
                            </div>
                        </div>

                        <!-- Linha: Débito -->
                        <div class="p-5 rounded-2xl bg-yellow-50/40 border border-yellow-100/50 space-y-4">
                            <div class="flex items-center justify-between border-b border-yellow-100/50 pb-2">
                                <h3 class="text-sm font-bold text-yellow-800 flex items-center gap-2"><i class="fa-solid fa-credit-card"></i> Cartão de Débito</h3>
                                <span class="text-[11px] text-yellow-600 font-semibold bg-yellow-100/40 px-2.5 py-0.5 rounded-full">Lançamento de Débito</span>
                            </div>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                <div class="form-group">
                                    <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valores do Sistema (R$)</label>
                                    <input type="number" step="0.01" id="debito-sistema" placeholder="0,00" class="w-full bg-white border border-slate-200 focus:border-blue-500 rounded-lg py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                                </div>
                                <div class="form-group">
                                    <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valores na Máquina (R$)</label>
                                    <input type="number" step="0.01" id="debito-fisico" placeholder="0,00" class="w-full bg-white border border-slate-200 focus:border-blue-500 rounded-lg py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                                </div>
                            </div>
                        </div>

                        <div class="flex gap-4">
                            <button type="button" id="btn-cancelar-edicao" onclick="cancelarEdicaoCaixa()" class="hidden flex-1 py-3 bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold rounded-xl text-sm transition">
                                Cancelar Edição
                            </button>
                            <button type="submit" class="flex-1 py-3.5 bg-blue-600 hover:bg-blue-700 active:bg-blue-800 text-white font-bold rounded-xl shadow-lg shadow-blue-100 transition-all flex items-center justify-center gap-2 text-sm">
                                <i class="fa-solid fa-cloud-arrow-up"></i> <span id="submit-fechamento-text">Salvar Fechamento Diário</span>
                            </button>
                        </div>
                    </div>
                </form>
            </div>

            <!-- Aba 4: Retiradas -->
            <div id="retiradas-tab" class="tab-content hidden space-y-6">
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                    <!-- Cadastrar Retirada -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm h-fit">
                        <h2 class="font-bold text-slate-900 text-base mb-4 flex items-center gap-2"><i class="fa-solid fa-hand-holding-dollar text-red-500"></i> Registrar Nova Retirada</h2>
                        <form id="form-retirada" onsubmit="salvarRetirada(event)" class="space-y-4">
                            <div class="form-group">
                                <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Data da Retirada</label>
                                <input type="date" id="data-retirada" class="w-full bg-slate-50 border border-slate-200 focus:border-red-500 focus:bg-white rounded-xl py-2 px-3 text-sm font-semibold outline-none transition" required>
                            </div>
                            <div class="form-group">
                                <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Tipo de Retirada</label>
                                <select id="categoria-retirada" class="w-full bg-slate-50 border border-slate-200 focus:border-red-500 focus:bg-white rounded-xl py-2 px-3 text-sm font-semibold outline-none transition" required>
                                    <option value="taxa_maquina">Taxa da Máquina</option>
                                    <option value="sangria">Sangria (Dinheiro)</option>
                                    <option value="saida_dia">Saídas do Dia (Despesas)</option>
                                    <option value="outros">Outros</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valor da Retirada (R$)</label>
                                <input type="number" step="0.01" id="valor-retirada" placeholder="0,00" class="w-full bg-slate-50 border border-slate-200 focus:border-red-500 focus:bg-white rounded-xl py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                            </div>
                            <div class="form-group">
                                <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Descrição / Justificativa</label>
                                <input type="text" id="desc-retirada" placeholder="Ex: Pagamento fornecedor Heineken" class="w-full bg-slate-50 border border-slate-200 focus:border-red-500 focus:bg-white rounded-xl py-2 px-3 text-sm font-semibold outline-none transition" required>
                            </div>
                            <button type="submit" class="w-full py-2.5 bg-red-600 hover:bg-red-700 text-white font-bold rounded-xl text-sm transition-all shadow-md shadow-red-100 flex items-center justify-center gap-2">
                                <i class="fa-solid fa-plus"></i> Registrar Retirada
                            </button>
                        </form>
                    </div>

                    <!-- Lista de Retiradas do Período -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm lg:col-span-2 flex flex-col">
                        <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 border-b border-slate-100 pb-4 mb-4">
                            <div>
                                <h2 class="font-bold text-slate-900 text-base flex items-center gap-2"><i class="fa-solid fa-list-ul text-red-500"></i> Registro de Retiradas Realizadas</h2>
                                <p class="text-xs text-slate-400">Fluxo de caixa de saídas de recursos do caixa</p>
                            </div>
                            <div class="relative max-w-xs w-full">
                                <i class="fa-solid fa-magnifying-glass absolute left-3 top-3 text-slate-400 text-xs"></i>
                                <input type="text" id="busca-retirada-desc" oninput="renderizarRetiradas()" placeholder="Filtrar por descrição..." class="w-full pl-8 pr-3 py-2 bg-slate-50 border border-slate-200 rounded-xl text-xs outline-none focus:border-red-500 focus:bg-white transition">
                            </div>
                        </div>

                        <!-- Filtro Categoria Retirada -->
                        <div class="flex gap-1.5 mb-4 overflow-x-auto pb-1">
                            <button onclick="setRetiradaFilter('todos')" id="ret-filter-todos" class="ret-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-800 text-white transition whitespace-nowrap">Todas</button>
                            <button onclick="setRetiradaFilter('taxa_maquina')" id="ret-filter-taxa_maquina" class="ret-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-100 text-slate-500 hover:bg-slate-200 transition whitespace-nowrap">Taxas</button>
                            <button onclick="setRetiradaFilter('sangria')" id="ret-filter-sangria" class="ret-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-100 text-slate-500 hover:bg-slate-200 transition whitespace-nowrap">Sangrias</button>
                            <button onclick="setRetiradaFilter('saida_dia')" id="ret-filter-saida_dia" class="ret-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-100 text-slate-500 hover:bg-slate-200 transition whitespace-nowrap">Saídas</button>
                            <button onclick="setRetiradaFilter('outros')" id="ret-filter-outros" class="ret-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-100 text-slate-500 hover:bg-slate-200 transition whitespace-nowrap">Outros</button>
                        </div>

                        <!-- Tabela de Retiradas -->
                        <div class="overflow-x-auto flex-1">
                            <table class="w-full text-left">
                                <thead>
                                    <tr class="border-b border-slate-200 text-xs text-slate-400 uppercase tracking-wider">
                                        <th class="pb-3 font-semibold">Data</th>
                                        <th class="pb-3 font-semibold">Categoria</th>
                                        <th class="pb-3 font-semibold">Descrição / Motivo</th>
                                        <th class="pb-3 font-semibold text-right">Valor</th>
                                        <th class="pb-3 font-semibold text-right">Ações</th>
                                    </tr>
                                </thead>
                                <tbody id="tabela-retiradas-corpo" class="divide-y divide-slate-100 text-sm">
                                    <!-- Dinâmico -->
                                </tbody>
                            </table>
                            <div id="sem-retiradas-warning" class="hidden text-center py-10 text-slate-400 text-xs">
                                <i class="fa-solid fa-folder-open text-3xl mb-2 block text-slate-200"></i>
                                Nenhuma retirada encontrada.
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Aba 5: Fiados -->
            <div id="fiados-tab" class="tab-content hidden space-y-6">
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                    <!-- Cadastrar Novo Fiado -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm h-fit">
                        <h2 class="font-bold text-slate-900 text-base mb-4 flex items-center gap-2"><i class="fa-solid fa-user-plus text-orange-500"></i> Registrar Novo Fiado</h2>
                        <form id="form-fiado" onsubmit="salvarFiado(event)" class="space-y-4">
                            <div class="form-group">
                                <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Data do Lançamento</label>
                                <input type="date" id="data-fiado" class="w-full bg-slate-50 border border-slate-200 focus:border-orange-500 focus:bg-white rounded-xl py-2 px-3 text-sm font-semibold outline-none transition" required>
                            </div>
                            <div class="form-group">
                                <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Nome do Cliente</label>
                                <input type="text" id="cliente-fiado" placeholder="Ex: João Silva" class="w-full bg-slate-50 border border-slate-200 focus:border-orange-500 focus:bg-white rounded-xl py-2 px-3 text-sm font-semibold outline-none transition" required>
                            </div>
                            <div class="form-group">
                                <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider block mb-1">Valor Bruto (R$)</label>
                                <input type="number" step="0.01" id="valor-fiado" placeholder="0,00" class="w-full bg-slate-50 border border-slate-200 focus:border-orange-500 focus:bg-white rounded-xl py-2 px-3 text-sm font-semibold outline-none text-right transition" required>
                            </div>
                            <button type="submit" class="w-full py-2.5 bg-orange-600 hover:bg-orange-700 text-white font-bold rounded-xl text-sm transition-all shadow-md shadow-orange-100 flex items-center justify-center gap-2">
                                <i class="fa-solid fa-user-tag"></i> Registrar Fiado
                            </button>
                        </form>
                    </div>

                    <!-- Lista de Fiados Pendentes e Quitação -->
                    <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm lg:col-span-2 flex flex-col">
                        <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 border-b border-slate-100 pb-4 mb-4">
                            <div>
                                <h2 class="font-bold text-slate-900 text-base flex items-center gap-2"><i class="fa-solid fa-list-check text-orange-500"></i> Carteira de Clientes (Contas Fiado)</h2>
                                <p class="text-xs text-slate-400">Pesquise clientes e alterne o status de pagamento (Pendente / Pago)</p>
                            </div>
                            <div class="relative max-w-xs w-full">
                                <i class="fa-solid fa-magnifying-glass absolute left-3 top-3 text-slate-400 text-xs"></i>
                                <input type="text" id="busca-fiado-nome" oninput="renderizarFiados()" placeholder="Buscar cliente..." class="w-full pl-8 pr-3 py-2 bg-slate-50 border border-slate-200 rounded-xl text-xs outline-none focus:border-orange-500 focus:bg-white transition">
                            </div>
                        </div>

                        <!-- Filtro Status Fiados -->
                        <div class="flex gap-2 mb-4">
                            <button onclick="setFiadoFilter('todos')" id="fiado-filter-todos" class="fiado-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-800 text-white transition">Todos</button>
                            <button onclick="setFiadoFilter('pendente')" id="fiado-filter-pendente" class="fiado-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-100 text-slate-500 hover:bg-slate-200 transition">Pendentes</button>
                            <button onclick="setFiadoFilter('pago')" id="fiado-filter-pago" class="fiado-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-100 text-slate-500 hover:bg-slate-200 transition">Quitados</button>
                        </div>

                        <!-- Tabela de Fiados -->
                        <div class="overflow-x-auto flex-1">
                            <table class="w-full text-left">
                                <thead>
                                    <tr class="border-b border-slate-200 text-xs text-slate-400 uppercase tracking-wider">
                                        <th class="pb-3 font-semibold">Cliente</th>
                                        <th class="pb-3 font-semibold">Data Registro</th>
                                        <th class="pb-3 font-semibold text-right">Valor</th>
                                        <th class="pb-3 font-semibold text-center">Status</th>
                                        <th class="pb-3 font-semibold text-right">Ações</th>
                                    </tr>
                                </thead>
                                <tbody id="tabela-fiados-corpo" class="divide-y divide-slate-100 text-sm">
                                    <!-- Dinâmico -->
                                </tbody>
                            </table>
                            <div id="sem-fiados-warning" class="hidden text-center py-8 text-slate-400 text-xs">
                                <i class="fa-solid fa-folder-open text-3xl mb-2 block text-slate-200"></i>
                                Nenhum fiado registrado para este filtro.
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Aba 6: Histórico Detalhado -->
            <div id="historico-tab" class="tab-content hidden space-y-6">
                <!-- Filtros Avançados -->
                <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex flex-col md:flex-row md:items-center justify-between gap-4">
                    <div>
                        <h2 class="font-bold text-slate-900 text-base flex items-center gap-2"><i class="fa-solid fa-filter text-blue-600"></i> Filtros de Histórico</h2>
                        <p class="text-xs text-slate-400">Controle, edite e exporte relatórios consolidados</p>
                    </div>
                    <div class="flex flex-wrap items-center gap-3">
                        <select id="tipo-filtro" onchange="toggleFiltroInputs()" class="bg-slate-50 border border-slate-200 rounded-xl py-2 px-3 text-xs font-semibold outline-none focus:border-blue-500 transition">
                            <option value="todos">Todo o Histórico</option>
                            <option value="dia">Por Dia Específico</option>
                            <option value="mes">Por Mês</option>
                        </select>

                        <input type="date" id="busca-dia" onchange="renderizarRelatorioCompleto()" class="hidden bg-slate-50 border border-slate-200 rounded-xl py-1.5 px-3 text-xs font-semibold outline-none">
                        <input type="month" id="busca-mes" onchange="renderizarRelatorioCompleto()" class="hidden bg-slate-50 border border-slate-200 rounded-xl py-1.5 px-3 text-xs font-semibold outline-none">

                        <button onclick="exportarCSV()" class="bg-slate-100 hover:bg-slate-200 text-slate-700 font-semibold text-xs py-2 px-3.5 rounded-lg flex items-center gap-1.5 transition">
                            <i class="fa-solid fa-file-excel text-emerald-600"></i> Exportar Dados
                        </button>
                    </div>
                </div>

                <!-- Tabela de Histórico Consolidador -->
                <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                    <h2 class="font-bold text-slate-900 text-base mb-4 flex items-center gap-2"><i class="fa-solid fa-receipt text-blue-600"></i> Fechamentos de Caixa Registrados</h2>
                    
                    <div class="overflow-x-auto">
                        <table class="w-full text-left">
                            <thead>
                                <tr class="border-b border-slate-200 text-xs text-slate-400 uppercase tracking-wider">
                                    <th class="pb-3 font-semibold">Data</th>
                                    <th class="pb-3 font-semibold">Formato</th>
                                    <th class="pb-3 font-semibold text-right">Faturamento Sistema</th>
                                    <th class="pb-3 font-semibold text-right">Contagem Física/Máquina</th>
                                    <th class="pb-3 font-semibold text-right">Balanço</th>
                                    <th class="pb-3 font-semibold text-center">Status</th>
                                    <th class="pb-3 font-semibold text-right">Ações</th>
                                </tr>
                            </thead>
                            <tbody id="tabela-historico-corpo" class="divide-y divide-slate-100 text-sm">
                                <!-- Dinâmico -->
                            </tbody>
                        </table>
                        <div id="sem-fechamentos-warning" class="hidden text-center py-12 text-slate-400 text-xs">
                            <i class="fa-solid fa-box-open text-4xl mb-2 block text-slate-200"></i>
                            Nenhum registro de fechamento encontrado.
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </div>

    <!-- SDKs do Firebase -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInWithCustomToken, signInAnonymously, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, doc, setDoc, getDoc, collection, onSnapshot, updateDoc, deleteDoc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // Configuração do Firebase com Fallback Inteligente (Usa a config provida ou a padrão do ambiente)
        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {
            apiKey: "AIzaSyAZN-1E2MpiKl9TQeUtHfbmBU729Dk5VbQ",
            authDomain: "margestch.firebaseapp.com",
            projectId: "margestch",
            storageBucket: "margestch.firebasestorage.app",
            messagingSenderId: "68222331424",
            appId: "1:68222331424:web:17b102bc69bed9c58caa45",
            measurementId: "G-EPLNN64Q3B"
        };

        const app = initializeApp(firebaseConfig);
        const auth = getAuth(app);
        const db = getFirestore(app);

        // Identificação do App ID da plataforma
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';

        // Definição estrita de Coleções e Subcoleções no Firestore (REVISADO - REGRA 1)
        const colMovimentacoes = collection(db, 'artifacts', appId, 'public', 'data', 'movimentacoes');
        const colFiados = collection(db, 'artifacts', appId, 'public', 'data', 'fiados');
        const colRetiradas = collection(db, 'artifacts', appId, 'public', 'data', 'retiradas');

        // Variáveis de Estado Local Reativas
        let movimentacoes = [];
        let fiados = [];
        let retiradas = [];
        let analiseAtual = null;
        let idEdicaoAtiva = null;
        let activeTab = 'dashboard-tab';
        let currentDashPeriod = 'hoje';
        let currentFiadosFilter = 'todos';
        let currentRetiradasFilter = 'todos';

        // Inicialização com Autenticação (REGRA 3)
        const initAuth = async () => {
            try {
                if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
                    await signInWithCustomToken(auth, __initial_auth_token);
                } else {
                    await signInAnonymously(auth);
                }
            } catch (err) {
                console.error("Erro na autenticação do Firebase:", err);
                document.getElementById('firebase-status').className = "flex items-center gap-1.5 py-1.5 px-3 rounded-lg text-xs font-semibold bg-rose-50 text-rose-700 border border-rose-200";
                document.getElementById('firebase-status').innerHTML = `<i class="fa-solid fa-cloud-slash"></i> <span>Erro de Conexão</span>`;
            }
        };

        initAuth();

        onAuthStateChanged(auth, (user) => {
            if (!user) return;

            // Atualiza status visual de sincronização
            document.getElementById('firebase-status').className = "flex items-center gap-1.5 py-1.5 px-3 rounded-lg text-xs font-semibold bg-emerald-50 text-emerald-700 border border-emerald-200";
            document.getElementById('firebase-status').innerHTML = `<i class="fa-solid fa-cloud animate-pulse text-emerald-500"></i> <span>Nuvem Ativa</span>`;

            // Escuta reativa do Firestore (REGRA 2 - Filtros em memória local)
            onSnapshot(colMovimentacoes, (snapshot) => {
                movimentacoes = [];
                snapshot.forEach(doc => {
                    movimentacoes.push({ id: doc.id, ...doc.data() });
                });
                renderizarTudo();
            }, (error) => console.error("Erro em movimentacoes:", error));

            onSnapshot(colFiados, (snapshot) => {
                fiados = [];
                snapshot.forEach(doc => {
                    fiados.push({ id: doc.id, ...doc.data() });
                });
                renderizarTudo();
            }, (error) => console.error("Erro em fiados:", error));

            onSnapshot(colRetiradas, (snapshot) => {
                retiradas = [];
                snapshot.forEach(doc => {
                    retiradas.push({ id: doc.id, ...doc.data() });
                });
                renderizarTudo();
            }, (error) => console.error("Erro em retiradas:", error));
        });

        // Configuração Inicial de Datas na interface
        function configurarDatasIniciais() {
            const hoje = new Date();
            document.getElementById('current-date-header').textContent = hoje.toLocaleDateString('pt-BR');
            
            const diaFormatado = hoje.toISOString().split('T')[0];
            document.getElementById('data-movimento').value = diaFormatado;
            document.getElementById('data-fiado').value = diaFormatado;
            document.getElementById('data-retirada').value = diaFormatado;
            document.getElementById('busca-dia').value = diaFormatado;

            const mesFormatado = diaFormatado.substring(0, 7);
            document.getElementById('busca-mes').value = mesFormatado;
        }
        configurarDatasIniciais();

        // Alternância de Abas de Navegação
        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            document.getElementById(tabId).classList.remove('hidden');

            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('border-blue-600', 'text-blue-600');
                btn.classList.add('border-transparent', 'text-slate-500');
            });

            const currentBtn = document.getElementById(`btn-${tabId}`);
            if (currentBtn) {
                currentBtn.classList.remove('border-transparent', 'text-slate-500');
                currentBtn.classList.add('border-blue-600', 'text-blue-600');
            }

            activeTab = tabId;
            renderizarTudo();
        }

        function renderizarTudo() {
            if (activeTab === 'dashboard-tab') {
                renderizarDashboard();
            } else if (activeTab === 'fiados-tab') {
                renderizarFiados();
            } else if (activeTab === 'retiradas-tab') {
                renderizarRetiradas();
            } else if (activeTab === 'historico-tab') {
                renderizarRelatorioCompleto();
            }
        }

        // ==========================================
        //  MÓDULO: LEITOR AUTOMATIZADO COM IA
        // ==========================================
        function processarRelatorioTexto() {
            const text = document.getElementById('raw-report-text').value;
            if (!text.trim()) {
                showToast("Por favor, cole um relatório válido para auditar.", "danger");
                return;
            }

            const tabelaPrecos = {
                "império": { unitario: 6.00, pack: 52.00, alias: "Império Long Neck" },
                "imperio": { unitario: 6.00, pack: 52.00, alias: "Império Long Neck" },
                "itaipava": { unitario: 4.00, pack: 35.00, alias: "Itaipava Lata 350ml" },
                "devassa": { unitario: 3.00, pack: 36.00, alias: "Devassa Lata 350ml" },
                "caltron": { unitario: 2.00, pack: 18.00, alias: "Caltron" },
                "hotmas vermelho": { unitario: 1.00, pack: 10.00, alias: "Hotmas Vermelho" },
                "hotmas": { unitario: 1.00, pack: 10.00, alias: "Hotmas Vermelho" },
                "hotmas azul": { unitario: 1.00, pack: 10.00, alias: "Hotmas Azul" },
                "heineken": { unitario: 8.00, pack: 96.00, alias: "Heineken Long Neck 330ml" },
                "cristal": { unitario: 3.00, pack: 36.00, alias: "Cristal Lata 350ml" },
                "budweiser": { unitario: 6.00, pack: 72.00, alias: "Budweiser Lata 350ml" }
            };

            let totalEstoqueFisico = 0;
            let totalFaturamentoCalculado = 0;
            let produtosMapeados = {};

            let financeiro = { dinheiro: 0, pix: 0, credito: 0, debito: 0, fiado: 0 };

            const blocosVenda = text.split(/#\d+\s*\|/);

            blocosVenda.forEach(bloco => {
                const trimmedBloco = bloco.trim();
                if (!trimmedBloco) return;

                const linhaCabecalho = trimmedBloco.split('\n')[0];
                let metodoPagamento = "dinheiro";
                let isMisto = false;

                if (linhaCabecalho.toLowerCase().includes('dinheiro+pix')) {
                    isMisto = true;
                } else if (linhaCabecalho.toLowerCase().includes('pix')) {
                    metodoPagamento = "pix";
                } else if (linhaCabecalho.toLowerCase().includes('cartão') || linhaCabecalho.toLowerCase().includes('cartao') || linhaCabecalho.toLowerCase().includes('crédito') || linhaCabecalho.toLowerCase().includes('debito')) {
                    metodoPagamento = "credito";
                } else if (linhaCabecalho.toLowerCase().includes('fiado')) {
                    metodoPagamento = "fiado";
                }

                const matchTotalVenda = trimmedBloco.match(/TOTAL:\s*(?:R\$\s*)?([\d.,]+)/i);
                let totalVendaFinanceiro = 0;
                if (matchTotalVenda) {
                    totalVendaFinanceiro = parseFloat(matchTotalVenda[1].replace(/\./g, '').replace(',', '.'));
                    
                    if (isMisto) {
                        financeiro.dinheiro += (totalVendaFinanceiro / 2);
                        financeiro.pix += (totalVendaFinanceiro / 2);
                    } else {
                        financeiro[metodoPagamento] += totalVendaFinanceiro;
                    }
                    totalFaturamentoCalculado += totalVendaFinanceiro;
                }

                const linhasProduto = trimmedBloco.split('\n');
                linhasProduto.forEach(linha => {
                    const matchProd = linha.match(/·\s*([^x\n]+?)\s+x(\d+)\s+(?:R\$\s*)?([\d.,]+)/i);
                    if (matchProd) {
                        let nomeOriginal = matchProd[1].trim();
                        let nomeNormalizado = nomeOriginal.toLowerCase();
                        let qtdRegistrada = parseInt(matchProd[2]);
                        let totalLinha = parseFloat(matchProd[3].replace(/\./g, '').replace(',', '.'));
                        
                        let unitarioRegistrado = totalLinha / qtdRegistrada;
                        let unidadesFisicasCalculadas = qtdRegistrada;
                        let tipoDeSaida = "Unidade";
                        let unitarioReal = unitarioRegistrado;
                        let aliasAmigavel = nomeOriginal;

                        let mapeouPreco = false;
                        for (let chave in tabelaPrecos) {
                            if (nomeNormalizado.includes(chave)) {
                                const precoConfig = tabelaPrecos[chave];
                                aliasAmigavel = precoConfig.alias;
                                mapeouPreco = true;

                                if (Math.abs(unitarioRegistrado - precoConfig.pack) < Math.abs(unitarioRegistrado - precoConfig.unitario)) {
                                    unidadesFisicasCalculadas = qtdRegistrada * 12;
                                    tipoDeSaida = "Pack (12 un)";
                                    unitarioReal = precoConfig.pack;
                                } else {
                                    unidadesFisicasCalculadas = qtdRegistrada;
                                    tipoDeSaida = "Unidade";
                                    unitarioReal = precoConfig.unitario;
                                }
                                break;
                            }
                        }

                        if (!mapeouPreco) {
                            unidadesFisicasCalculadas = qtdRegistrada;
                            tipoDeSaida = "Unidade";
                            unitarioReal = unitarioRegistrado;
                        }

                        const chaveAgrupamento = aliasAmigavel + " - " + tipoDeSaida;
                        if (!produtosMapeados[chaveAgrupamento]) {
                            produtosMapeados[chaveAgrupamento] = {
                                nome: aliasAmigavel,
                                tipo: tipoDeSaida,
                                quantidadeFisica: 0,
                                faturamentoAcumulado: 0,
                                precoUnitarioRef: unitarioReal
                            };
                        }

                        produtosMapeados[chaveAgrupamento].quantidadeFisica += unidadesFisicasCalculadas;
                        produtosMapeados[chaveAgrupamento].faturamentoAcumulado += totalLinha;
                        totalEstoqueFisico += unidadesFisicasCalculadas;
                    }
                });
            });

            document.getElementById('leitor-total-fat').textContent = formatReal(totalFaturamentoCalculado);
            document.getElementById('leitor-total-itens').textContent = `${totalEstoqueFisico} un.`;
            document.getElementById('leitor-produtos-distintos').textContent = `${Object.keys(produtosMapeados).length} tipos`;

            document.getElementById('leitor-meio-dinheiro').textContent = formatReal(financeiro.dinheiro);
            document.getElementById('leitor-meio-pix').textContent = formatReal(financeiro.pix);
            document.getElementById('leitor-meio-credito').textContent = formatReal(financeiro.credito);
            document.getElementById('leitor-meio-debito').textContent = formatReal(financeiro.debito);
            document.getElementById('leitor-meio-fiado').textContent = formatReal(financeiro.fiado);

            const corpoTabela = document.getElementById('tabela-leitor-corpo');
            corpoTabela.innerHTML = '';

            for (let chave in produtosMapeados) {
                const item = produtosMapeados[chave];
                const tr = document.createElement('tr');
                tr.className = "border-b border-slate-100 hover:bg-slate-50 transition-colors";
                
                const badgeClass = item.tipo.includes('Pack') 
                    ? 'bg-purple-150 text-purple-700 border-purple-200 bg-purple-50' 
                    : 'bg-slate-100 text-slate-700 border-slate-200';

                tr.innerHTML = `
                    <td class="p-3 font-semibold text-slate-800">${item.nome}</td>
                    <td class="p-3">
                        <span class="inline-flex items-center px-2 py-0.5 rounded text-[10px] font-bold border ${badgeClass}">
                            ${item.tipo}
                        </span>
                    </td>
                    <td class="p-3 text-center font-bold text-slate-900">${item.quantidadeFisica} un.</td>
                    <td class="p-3 text-right text-slate-500">${formatReal(item.precoUnitarioRef)}</td>
                    <td class="p-3 text-right font-bold text-slate-950">${formatReal(item.faturamentoAcumulado)}</td>
                `;
                corpoTabela.appendChild(tr);
            }

            const applyBtn = document.getElementById('btn-aplicar-fechamento');
            applyBtn.removeAttribute('disabled');
            applyBtn.className = "py-2 px-3.5 bg-purple-600 hover:bg-purple-700 text-white font-bold rounded-xl text-xs transition-all flex items-center gap-1.5 cursor-pointer shadow-md shadow-purple-100";

            analiseAtual = financeiro;
            window.caixaAtualAuditado = financeiro;
            renderizarDashboard();

            showToast("Relatório auditado! Packs de 12 contados fisicamente.", "success");
        }

        function aplicarAoFechamento() {
            if (!analiseAtual) return;

            document.getElementById('dinheiro-sistema').value = analiseAtual.dinheiro.toFixed(2);
            document.getElementById('pix-sistema').value = analiseAtual.pix.toFixed(2);
            document.getElementById('credito-sistema').value = analiseAtual.credito.toFixed(2);
            document.getElementById('debito-sistema').value = analiseAtual.debito.toFixed(2);

            showToast("Valores integrados ao fechamento! Informe as contagens físicas.", "info");
            switchTab('lancamentos-tab');
        }

        function limparLeitor() {
            document.getElementById('raw-report-text').value = '';
            document.getElementById('leitor-total-fat').textContent = "R$ 0,00";
            document.getElementById('leitor-total-itens').textContent = "0 un.";
            document.getElementById('leitor-produtos-distintos').textContent = "0 cadastros";
            document.getElementById('leitor-meio-dinheiro').textContent = "R$ 0,00";
            document.getElementById('leitor-meio-pix').textContent = "R$ 0,00";
            document.getElementById('leitor-meio-credito').textContent = "R$ 0,00";
            document.getElementById('leitor-meio-debito').textContent = "R$ 0,00";
            document.getElementById('leitor-meio-fiado').textContent = "R$ 0,00";
            document.getElementById('tabela-leitor-corpo').innerHTML = `
                <tr>
                    <td colspan="5" class="p-8 text-center text-slate-400 italic">Insira e processe o texto para analisar as vendas do dia.</td>
                </tr>
            `;

            const applyBtn = document.getElementById('btn-aplicar-fechamento');
            applyBtn.setAttribute('disabled', 'true');
            applyBtn.className = "py-2 px-3.5 bg-slate-100 text-slate-400 font-bold rounded-xl text-xs transition-all flex items-center gap-1.5 cursor-not-allowed";
            analiseAtual = null;
            window.caixaAtualAuditado = null;
            renderizarDashboard();
        }

        // ==========================================
        //  MÓDULO: CONTROLE FINANCEIRO NO FIRESTORE
        // ==========================================
        async function salvarFechamento(event) {
            event.preventDefault();
            if (!auth.currentUser) return;

            const data = document.getElementById('data-movimento').value;
            const fechamentoId = idEdicaoAtiva ? idEdicaoAtiva : Date.now().toString();

            const fechamento = {
                id: fechamentoId,
                data: data,
                dinheiro: {
                    sistema: parseFloat(document.getElementById('dinheiro-sistema').value) || 0,
                    fisico: parseFloat(document.getElementById('dinheiro-fisico').value) || 0
                },
                pix: {
                    sistema: parseFloat(document.getElementById('pix-sistema').value) || 0,
                    fisico: parseFloat(document.getElementById('pix-fisico').value) || 0
                },
                credito: {
                    sistema: parseFloat(document.getElementById('credito-sistema').value) || 0,
                    fisico: parseFloat(document.getElementById('credito-fisico').value) || 0
                },
                debito: {
                    sistema: parseFloat(document.getElementById('debito-sistema').value) || 0,
                    fisico: parseFloat(document.getElementById('debito-fisico').value) || 0
                }
            };

            try {
                // Guarda de forma síncrona na nuvem (Firestore) - REGRA 1
                const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'movimentacoes', fechamentoId);
                await setDoc(docRef, fechamento);

                showToast("Fechamento guardado com sucesso na nuvem!", "success");
                cancelarEdicaoCaixa();
                switchTab('dashboard-tab');
            } catch (err) {
                console.error("Erro ao salvar fechamento:", err);
                showToast("Erro ao guardar na nuvem.", "danger");
            }
        }

        async function excluirMovimentacao(id) {
            if (!auth.currentUser) return;
            showConfirmModal(
                "Deletar Fechamento?", 
                "Isso apagará permanentemente o fechamento selecionado do banco de dados na nuvem. Deseja continuar?", 
                async () => {
                    try {
                        const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'movimentacoes', id);
                        await deleteDoc(docRef);
                        showToast("Fechamento diário excluído do banco de dados.", "danger");
                        renderizarDashboard();
                    } catch (err) {
                        console.error(err);
                        showToast("Erro ao excluir do banco de dados.", "danger");
                    }
                }
            );
        }

        function habilitarEdicaoCaixa(id) {
            const item = movimentacoes.find(m => m.id === id);
            if (!item) return;

            idEdicaoAtiva = id;
            document.getElementById('data-movimento').value = item.data;
            document.getElementById('dinheiro-sistema').value = item.dinheiro.sistema;
            document.getElementById('dinheiro-fisico').value = item.dinheiro.fisico;
            
            document.getElementById('pix-sistema').value = item.pix.sistema;
            document.getElementById('pix-fisico').value = item.pix.fisico;
            
            document.getElementById('credito-sistema').value = item.credito.sistema;
            document.getElementById('credito-fisico').value = item.credito.fisico;
            
            document.getElementById('debito-sistema').value = item.debito.sistema;
            document.getElementById('debito-fisico').value = item.debito.fisico;

            document.getElementById('edit-indicator').classList.remove('hidden');
            document.getElementById('btn-cancelar-edicao').classList.remove('hidden');
            document.getElementById('submit-fechamento-text').textContent = "Atualizar Fechamento Diário";

            showToast("Fechamento de caixa carregado para edição!", "info");
            switchTab('lancamentos-tab');
        }

        function cancelarEdicaoCaixa() {
            idEdicaoAtiva = null;
            document.getElementById('form-fechamento').reset();
            configurarDatasIniciais();
            document.getElementById('edit-indicator').classList.add('hidden');
            document.getElementById('btn-cancelar-edicao').classList.add('hidden');
            document.getElementById('submit-fechamento-text').textContent = "Salvar Fechamento Diário";
        }

        // ==========================================
        //  MÓDULO: RETIRADAS NO FIRESTORE
        // ==========================================
        function setRetiradaFilter(filter) {
            currentRetiradasFilter = filter;
            document.querySelectorAll('.ret-filter-btn').forEach(btn => {
                btn.className = "ret-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-100 text-slate-500 hover:bg-slate-200 transition whitespace-nowrap";
            });
            const activeBtn = document.getElementById(`ret-filter-${filter}`);
            if (activeBtn) activeBtn.className = "ret-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-800 text-white transition whitespace-nowrap";
            renderizarRetiradas();
        }

        async function salvarRetirada(event) {
            event.preventDefault();
            if (!auth.currentUser) return;

            const retiradaId = Date.now().toString();
            const novaRetirada = {
                id: retiradaId,
                data: document.getElementById('data-retirada').value,
                categoria: document.getElementById('categoria-retirada').value,
                valor: parseFloat(document.getElementById('valor-retirada').value) || 0,
                desc: document.getElementById('desc-retirada').value.trim()
            };

            try {
                const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'retiradas', retiradaId);
                await setDoc(docRef, novaRetirada);

                showToast("Retirada registada na nuvem!", "success");
                document.getElementById('form-retirada').reset();
                configurarDatasIniciais();
            } catch (err) {
                console.error(err);
                showToast("Erro ao registar retirada.", "danger");
            }
        }

        async function excluirRetirada(id) {
            if (!auth.currentUser) return;
            showConfirmModal(
                "Remover Retirada?", 
                "Deseja excluir permanentemente o registo desta retirada do banco de dados?", 
                async () => {
                    try {
                        const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'retiradas', id);
                        await deleteDoc(docRef);
                        showToast("Retirada removida do caixa na nuvem.", "danger");
                    } catch (err) {
                        console.error(err);
                        showToast("Erro ao remover retirada.", "danger");
                    }
                }
            );
        }

        function renderizarRetiradas() {
            const corpo = document.getElementById('tabela-retiradas-corpo');
            const query = document.getElementById('busca-retirada-desc').value.toLowerCase();
            const warning = document.getElementById('sem-retiradas-warning');

            corpo.innerHTML = '';
            let filtrados = retiradas;

            if (currentRetiradasFilter !== 'todos') {
                filtrados = filtrados.filter(r => r.categoria === currentRetiradasFilter);
            }

            if (query) {
                filtrados = filtrados.filter(r => r.desc.toLowerCase().includes(query));
            }

            if (filtrados.length === 0) {
                warning.classList.remove('hidden');
                return;
            }
            warning.classList.add('hidden');

            filtrados.sort((a, b) => new Date(b.data) - new Date(a.data));

            const catLabels = {
                taxa_maquina: 'Taxa da Máquina',
                sangria: 'Sangria',
                saida_dia: 'Saídas do Dia',
                outros: 'Outros'
            };

            filtrados.forEach(r => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition-colors";
                tr.innerHTML = `
                    <td class="py-3 px-1 text-slate-500">${formatarDataBR(r.data)}</td>
                    <td class="py-3 px-1 font-semibold text-slate-700">${catLabels[r.categoria]}</td>
                    <td class="py-3 px-1 text-slate-600">${r.desc}</td>
                    <td class="py-3 px-1 text-right font-bold text-red-600">${formatReal(r.valor)}</td>
                    <td class="py-3 px-1 text-right">
                        <button onclick="excluirRetirada('${r.id}')" class="p-1 px-2.5 bg-rose-50 hover:bg-rose-100 text-rose-600 rounded-lg text-xs font-bold transition">
                            <i class="fa-solid fa-trash-can"></i>
                        </button>
                    </td>
                `;
                corpo.appendChild(tr);
            });
        }

        // ==========================================
        //  MÓDULO: CONTROLE DE FIADOS NO FIRESTORE
        // ==========================================
        function setFiadoFilter(filter) {
            currentFiadosFilter = filter;
            document.querySelectorAll('.fiado-filter-btn').forEach(btn => {
                btn.className = "fiado-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-100 text-slate-500 hover:bg-slate-200 transition";
            });
            const activeBtn = document.getElementById(`fiado-filter-${filter}`);
            if (activeBtn) activeBtn.className = "fiado-filter-btn px-3 py-1.5 rounded-lg text-xs font-semibold bg-slate-800 text-white transition";
            renderizarFiados();
        }

        async function salvarFiado(event) {
            event.preventDefault();
            if (!auth.currentUser) return;

            const fiadoId = Date.now().toString();
            const novoFiado = {
                id: fiadoId,
                data: document.getElementById('data-fiado').value,
                cliente: document.getElementById('cliente-fiado').value.trim(),
                valor: parseFloat(document.getElementById('valor-fiado').value) || 0,
                status: 'pendente'
            };

            try {
                const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'fiados', fiadoId);
                await setDoc(docRef, novoFiado);

                showToast(`Fiado para ${novoFiado.cliente} guardado na nuvem!`, "success");
                document.getElementById('form-fiado').reset();
                configurarDatasIniciais();
            } catch (err) {
                console.error(err);
                showToast("Erro ao guardar fiado.", "danger");
            }
        }

        async function toggleStatusFiado(id) {
            if (!auth.currentUser) return;
            const item = fiados.find(f => f.id === id);
            if (item) {
                try {
                    const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'fiados', id);
                    await updateDoc(docRef, {
                        status: item.status === 'pendente' ? 'pago' : 'pendente'
                    });
                    showToast(`Status de ${item.cliente} atualizado!`, "info");
                } catch (err) {
                    console.error(err);
                }
            }
        }

        async function excluirFiado(id) {
            if (!auth.currentUser) return;
            showConfirmModal(
                "Remover Registro?", 
                "Deseja excluir permanentemente este lançamento de fiado na nuvem?", 
                async () => {
                    try {
                        const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'fiados', id);
                        await deleteDoc(docRef);
                        showToast("Registo removido da nuvem com sucesso.", "danger");
                    } catch (err) {
                        console.error(err);
                        showToast("Erro ao remover fiado.", "danger");
                    }
                }
            );
        }

        function renderizarFiados() {
            const corpo = document.getElementById('tabela-fiados-corpo');
            const query = document.getElementById('busca-fiado-nome').value.toLowerCase();
            const warning = document.getElementById('sem-fiados-warning');
            
            corpo.innerHTML = '';
            let filtrados = fiados;

            if (currentFiadosFilter === 'pendente') {
                filtrados = fiados.filter(f => f.status === 'pendente');
            } else if (currentFiadosFilter === 'pago') {
                filtrados = fiados.filter(f => f.status === 'pago');
            }

            if (query) {
                filtrados = filtrados.filter(f => f.cliente.toLowerCase().includes(query));
            }

            if (filtrados.length === 0) {
                warning.classList.remove('hidden');
                return;
            }
            warning.classList.add('hidden');

            filtrados.sort((a, b) => new Date(b.data) - new Date(a.data));

            filtrados.forEach(f => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition-colors";

                const badgeClass = f.status === 'pendente' 
                    ? 'bg-orange-50 text-orange-700 border-orange-200' 
                    : 'bg-emerald-50 text-emerald-700 border-emerald-200';
                
                const badgeText = f.status === 'pendente' ? 'Pendente' : 'Quitado';

                tr.innerHTML = `
                    <td class="py-3 px-1 font-semibold text-slate-800">${f.cliente}</td>
                    <td class="py-3 px-1 text-slate-500">${formatarDataBR(f.data)}</td>
                    <td class="py-3 px-1 text-right font-bold text-slate-900">${formatReal(f.valor)}</td>
                    <td class="py-3 px-1 text-center">
                        <span class="inline-flex items-center px-2 py-1 text-xs font-semibold rounded-lg border ${badgeClass}">
                            ${badgeText}
                        </span>
                    </td>
                    <td class="py-3 px-1 text-right space-x-1 whitespace-nowrap">
                        <button onclick="toggleStatusFiado('${f.id}')" title="Trocar Status" class="p-1 px-2.5 bg-slate-100 hover:bg-slate-200 text-slate-700 rounded-lg text-xs font-bold transition">
                            <i class="fa-solid ${f.status === 'pendente' ? 'fa-check text-emerald-600' : 'fa-rotate-left text-amber-600'}"></i>
                        </button>
                        <button onclick="excluirFiado('${f.id}')" class="p-1 px-2.5 bg-rose-50 hover:bg-rose-100 text-rose-600 rounded-lg text-xs font-bold transition">
                            <i class="fa-solid fa-trash-can"></i>
                        </button>
                    </td>
                `;
                corpo.appendChild(tr);
            });
        }

        // ==========================================
        //  REGRAS DO DASHBOARD & ACUMULADOS
        // ==========================================
        function setDashboardPeriod(periodo) {
            currentDashPeriod = periodo;
            document.querySelectorAll('.dash-period-btn').forEach(btn => {
                btn.className = "dash-period-btn px-3 py-1.5 rounded-md text-xs font-semibold text-slate-500 hover:text-slate-800 transition";
            });
            const activeBtn = document.getElementById(`dash-p-${periodo}`);
            if (activeBtn) activeBtn.className = "dash-period-btn px-3 py-1.5 rounded-md text-xs font-semibold bg-white text-slate-800 shadow-sm transition";
            
            const desc = document.getElementById('dash-periodo-desc');
            if (periodo === 'hoje') desc.textContent = "Mostrando dados de hoje";
            else if (periodo === 'mes') desc.textContent = "Mostrando acumulado deste mês";
            else desc.textContent = "Mostrando histórico acumulado geral";

            renderizarDashboard();
        }

        function obterFiltroDataDashboard() {
            const hoje = new Date();
            const hojeStr = hoje.toISOString().split('T')[0];
            const mesCorrente = hojeStr.substring(0, 7);

            if (currentDashPeriod === 'hoje') {
                return (data) => data === hojeStr;
            } else if (currentDashPeriod === 'mes') {
                return (data) => data.startsWith(mesCorrente);
            }
            return () => true;
        }

        function renderizarDashboard() {
            const filtro = obterFiltroDataDashboard();

            const closingsFiltrados = movimentacoes.filter(m => filtro(m.data));
            const retiradasFiltradas = retiradas.filter(r => filtro(r.data));

            let totalDinheiroFisico = 0, totalDinheiroSis = 0;
            let totalPixFisico = 0, totalPixSis = 0;
            let totalCreditoFisico = 0, totalCreditoSis = 0;
            let totalDebitoFisico = 0, totalDebitoSis = 0;

            closingsFiltrados.forEach(m => {
                totalDinheiroFisico += m.dinheiro.fisico;
                totalDinheiroSis += m.dinheiro.sistema;
                totalPixFisico += m.pix.fisico;
                totalPixSis += m.pix.sistema;
                totalCreditoFisico += m.credito ? m.credito.fisico : 0;
                totalCreditoSis += m.credito ? m.credito.sistema : 0;
                totalDebitoFisico += m.debito ? m.debito.fisico : 0;
                totalDebitoSis += m.debito ? m.debito.sistema : 0;
            });

            if (currentDashPeriod === 'hoje' && closingsFiltrados.length === 0 && window.caixaAtualAuditado) {
                totalDinheiroSis = window.caixaAtualAuditado.dinheiro;
                totalPixSis = window.caixaAtualAuditado.pix;
                totalCreditoSis = window.caixaAtualAuditado.credito;
                totalDebitoSis = window.caixaAtualAuditado.debito;

                totalDinheiroFisico = window.caixaAtualAuditado.dinheiro;
                totalPixFisico = window.caixaAtualAuditado.pix;
                totalCreditoFisico = window.caixaAtualAuditado.credito;
                totalDebitoFisico = window.caixaAtualAuditado.debito;
            }

            let totalTaxaMaquina = 0;
            let totalSangria = 0;
            let totalSaidaDia = 0;
            let totalOutros = 0;

            retiradasFiltradas.forEach(r => {
                if (r.categoria === 'taxa_maquina') totalTaxaMaquina += r.valor;
                else if (r.categoria === 'sangria') totalSangria += r.valor;
                else if (r.categoria === 'saida_dia') totalSaidaDia += r.valor;
                else if (r.categoria === 'outros') totalOutros += r.valor;
            });

            const totalRetiradasBruto = totalTaxaMaquina + totalSangria + totalSaidaDia + totalOutros;

            const fiadosPendentes = fiados.filter(f => f.status === 'pendente');
            const totalFiadoPendente = fiadosPendentes.reduce((acc, curr) => acc + curr.valor, 0);

            document.getElementById('dash-val-dinheiro').textContent = formatReal(totalDinheiroFisico);
            document.getElementById('dash-val-pix').textContent = formatReal(totalPixFisico);
            
            const totalCartaoFisico = totalCreditoFisico + totalDebitoFisico;
            document.getElementById('dash-val-cartao').textContent = formatReal(totalCartaoFisico);
            document.getElementById('dash-cartao-split-summary').textContent = `${formatReal(totalCreditoFisico)} / ${formatReal(totalDebitoFisico)}`;

            document.getElementById('dash-val-retiradas').textContent = formatReal(totalRetiradasBruto);
            document.getElementById('dash-retiradas-split-summary').textContent = `S: ${formatReal(totalSangria)} / D: ${formatReal(totalSaidaDia)}`;

            document.getElementById('dash-val-fiado').textContent = formatReal(totalFiadoPendente);
            document.getElementById('dash-fiados-ativos-count').textContent = fiadosPendentes.length;

            const balancoFisicoLiquido = (totalDinheiroFisico + totalPixFisico + totalCartaoFisico) - totalRetiradasBruto;
            document.getElementById('dash-val-total').textContent = formatReal(balancoFisicoLiquido);

            const difDinheiro = totalDinheiroFisico - totalDinheiroSis;
            const difPix = totalPixFisico - totalPixSis;
            const difCredito = totalCreditoFisico - totalCreditoSis;
            const difDebito = totalDebitoFisico - totalDebitoSis;
            const balancoFinalDiferenca = difDinheiro + difPix + difCredito + difDebito;

            formatarDiferencaBadge('dash-dif-dinheiro', difDinheiro);
            formatarDiferencaBadge('dash-dif-pix', difPix);
            formatarDiferencaBadge('dash-dif-cartao', difCredito + difDebito);
            formatarDiferencaBadge('dash-balanco-final', balancoFinalDiferenca, true);

            document.getElementById('desp-taxas').textContent = formatReal(totalTaxaMaquina);
            document.getElementById('desp-sangria').textContent = formatReal(totalSangria);
            document.getElementById('desp-saidas').textContent = formatReal(totalSaidaDia);
            document.getElementById('desp-outros').textContent = formatReal(totalOutros);

            const maxValor = Math.max(totalDinheiroSis, totalDinheiroFisico, totalPixSis, totalPixFisico, totalCreditoSis, totalCreditoFisico, totalDebitoSis, totalDebitoFisico, 1);

            document.getElementById('bar-dinheiro-sis').textContent = formatReal(totalDinheiroSis);
            document.getElementById('bar-dinheiro-fis').textContent = formatReal(totalDinheiroFisico);
            document.getElementById('bar-dinheiro-sis-fill').style.width = `${(totalDinheiroSis / maxValor) * 100}%`;
            document.getElementById('bar-dinheiro-fis-fill').style.width = `${(totalDinheiroFisico / maxValor) * 100}%`;

            document.getElementById('bar-pix-sis').textContent = formatReal(totalPixSis);
            document.getElementById('bar-pix-fis').textContent = formatReal(totalPixFisico);
            document.getElementById('bar-pix-sis-fill').style.width = `${(totalPixSis / maxValor) * 100}%`;
            document.getElementById('bar-pix-fis-fill').style.width = `${(totalPixFisico / maxValor) * 100}%`;

            document.getElementById('bar-credito-sis').textContent = formatReal(totalCreditoSis);
            document.getElementById('bar-credito-fis').textContent = formatReal(totalCreditoFisico);
            document.getElementById('bar-credito-sis-fill').style.width = `${(totalCreditoSis / maxValor) * 100}%`;
            document.getElementById('bar-credito-fis-fill').style.width = `${(totalCreditoFisico / maxValor) * 100}%`;

            document.getElementById('bar-debito-sis').textContent = formatReal(totalDebitoSis);
            document.getElementById('bar-debito-fis').textContent = formatReal(totalDebitoFisico);
            document.getElementById('bar-debito-sis-fill').style.width = `${(totalDebitoSis / maxValor) * 100}%`;
            document.getElementById('bar-debito-fis-fill').style.width = `${(totalDebitoFisico / maxValor) * 100}%`;
        }

        // ==========================================
        //  REGRAS DE FILTRO E HISTÓRICO COMPLETO
        // ==========================================
        function toggleFiltroInputs() {
            const tipo = document.getElementById('tipo-filtro').value;
            
            document.getElementById('busca-dia').classList.add('hidden');
            document.getElementById('busca-mes').classList.add('hidden');

            if (tipo === 'dia') {
                document.getElementById('busca-dia').classList.remove('hidden');
            } else if (tipo === 'mes') {
                document.getElementById('busca-mes').classList.remove('hidden');
            }
            renderizarRelatorioCompleto();
        }

        function renderizarRelatorioCompleto() {
            const corpo = document.getElementById('tabela-historico-corpo');
            const warning = document.getElementById('sem-fechamentos-warning');
            const tipo = document.getElementById('tipo-filtro').value;

            corpo.innerHTML = '';
            let filtrados = [...movimentacoes];

            if (tipo === 'dia') {
                const dia = document.getElementById('busca-dia').value;
                filtrados = filtrados.filter(m => m.data === dia);
            } else if (tipo === 'mes') {
                const mes = document.getElementById('busca-mes').value;
                filtrados = filtrados.filter(m => m.data.startsWith(mes));
            }

            if (filtrados.length === 0) {
                warning.classList.remove('hidden');
                return;
            }
            warning.classList.add('hidden');

            filtrados.sort((a, b) => new Date(b.data) - new Date(a.data));

            filtrados.forEach(m => {
                const subCategorias = [
                    { nome: 'Dinheiro', sis: m.dinheiro.sistema, fis: m.dinheiro.fisico, icon: 'fa-money-bill-wave text-red-500' },
                    { nome: 'Pix', sis: m.pix.sistema, fis: m.pix.fisico, icon: 'fa-brands fa-pix text-sky-500' },
                    { nome: 'Crédito', sis: m.credito ? m.credito.sistema : 0, fis: m.credito ? m.credito.fisico : 0, icon: 'fa-credit-card text-amber-500' },
                    { nome: 'Débito', sis: m.debito ? m.debito.sistema : 0, fis: m.debito ? m.debito.fisico : 0, icon: 'fa-credit-card text-yellow-500' }
                ];

                subCategorias.forEach((metodo, idx) => {
                    const tr = document.createElement('tr');
                    tr.className = "hover:bg-slate-50 transition-colors border-b border-slate-100";
                    
                    const dif = metodo.fis - metodo.sis;
                    let badgeClass = "bg-slate-100 text-slate-700";
                    let badgeText = "OK";

                    if (dif > 0) {
                        badgeClass = "bg-emerald-50 text-emerald-700";
                        badgeText = "Sobra";
                    } else if (dif < 0) {
                        badgeClass = "bg-rose-50 text-rose-700";
                        badgeText = "Quebra";
                    }

                    const acoes = idx === 0 
                        ? `<div class="flex justify-end gap-1.5 whitespace-nowrap">
                                <button onclick="habilitarEdicaoCaixa('${m.id}')" class="p-1 px-2.5 bg-amber-50 hover:bg-amber-100 text-amber-700 rounded-lg text-xs font-bold transition">
                                    <i class="fa-solid fa-pen-to-square"></i> Editar
                                </button>
                                <button onclick="excluirMovimentacao('${m.id}')" class="p-1 px-2.5 bg-rose-50 hover:bg-rose-100 text-rose-600 rounded-lg text-xs font-bold transition">
                                    <i class="fa-solid fa-trash-can"></i> Excluir
                                </button>
                           </div>` 
                        : '';

                    tr.innerHTML = `
                        <td class="py-3 px-1 font-semibold text-slate-800 ${idx === 0 ? '' : 'opacity-20'}">${idx === 0 ? formatarDataBR(m.data) : ''}</td>
                        <td class="py-3 px-1 text-slate-600 font-medium"><i class="fa-solid ${metodo.icon} mr-1.5 text-xs"></i> ${metodo.nome}</td>
                        <td class="py-3 px-1 text-right text-slate-500 font-mono">${formatReal(metodo.sis)}</td>
                        <td class="py-3 px-1 text-right text-slate-800 font-bold font-mono">${formatReal(metodo.fis)}</td>
                        <td class="py-3 px-1 text-right font-bold font-mono ${dif >= 0 ? 'text-emerald-600' : 'text-rose-600'}">${(dif >= 0 ? '+' : '') + formatReal(dif)}</td>
                        <td class="py-3 px-1 text-center">
                            <span class="inline-flex items-center px-2 py-0.5 text-xs font-semibold rounded ${badgeClass}">
                                ${badgeText}
                            </span>
                        </td>
                        <td class="py-3 px-1 text-right">${acoes}</td>
                    `;
                    corpo.appendChild(tr);
                });
            });
        }

        // ==========================================
        //  REDEFINIR BANCO DE DADOS (LIMPEZA COMPLETA)
        // ==========================================
        async function limparTudo() {
            if (!auth.currentUser) return;
            showConfirmModal(
                "Redefinir Banco de Dados na Nuvem?", 
                "Todos os lançamentos, retiradas e fiados salvos no Firebase serão deletados definitivamente.", 
                async () => {
                    try {
                        showToast("Limpando banco de dados...", "info");
                        
                        // Executa de forma sequencial para garantir o delete de todos os documentos
                        for (let m of movimentacoes) {
                            await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', 'movimentacoes', m.id));
                        }
                        for (let f of fiados) {
                            await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', 'fiados', f.id));
                        }
                        for (let r of retiradas) {
                            await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', 'retiradas', r.id));
                        }

                        showToast("Banco de dados reiniciado na nuvem com sucesso!", "danger");
                        configurarDatasIniciais();
                        renderizarTudo();
                    } catch (err) {
                        console.error(err);
                        showToast("Erro ao redefinir banco de dados.", "danger");
                    }
                }
            );
        }

        function exportarCSV() {
            if (movimentacoes.length === 0 && fiados.length === 0 && retiradas.length === 0) {
                showToast("Nenhum dado disponível no período.", "danger");
                return;
            }

            let csvContent = "data:text/csv;charset=utf-8,\uFEFF";
            csvContent += "FECHAMENTOS DE CAIXA\n";
            csvContent += "Data;Formato de Pagamento;Valores do Sistema;Valores Físicos / na Máquina;Diferença\n";
            movimentacoes.forEach(m => {
                csvContent += `${formatarDataBR(m.data)};Dinheiro;${m.dinheiro.sistema};${m.dinheiro.fisico};${m.dinheiro.fisico - m.dinheiro.sistema}\n`;
                csvContent += `${formatarDataBR(m.data)};Pix;${m.pix.sistema};${m.pix.fisico};${m.pix.fisico - m.pix.sistema}\n`;
                
                const cSis = m.credito ? m.credito.sistema : 0;
                const cFis = m.credito ? m.credito.fisico : 0;
                csvContent += `${formatarDataBR(m.data)};Crédito;${cSis};${cFis};${cFis - cSis}\n`;
                
                const dSis = m.debito ? m.debito.sistema : 0;
                const dFis = m.debito ? m.debito.fisico : 0;
                csvContent += `${formatarDataBR(m.data)};Débito;${dSis};${dFis};${dFis - dSis}\n`;
            });

            csvContent += "\n\nRETIRADAS E DESPESAS\n";
            csvContent += "Data;Categoria;Descricao;Valor\n";
            retiradas.forEach(r => {
                csvContent += `${formatarDataBR(r.data)};${r.categoria};${r.desc};${r.valor}\n`;
            });

            csvContent += "\n\nCONTROLE DE FIADOS (CLIENTES)\n";
            csvContent += "Data;Cliente;Valor;Status\n";
            fiados.forEach(f => {
                csvContent += `${formatarDataBR(f.data)};${f.cliente};${f.valor};${f.status === 'pendente' ? 'Pendente' : 'Quitado'}\n`;
            });

            const encodedUri = encodeURI(csvContent);
            const link = document.createElement("a");
            link.setAttribute("href", encodedUri);
            link.setAttribute("download", `Planilha_FluxoCompleto_${new Date().toISOString().split('T')[0]}.csv`);
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);

            showToast("Relatório exportado!", "success");
        }

        // Tornando todas as funções globais para escopo compatível com o layout HTML
        window.switchTab = switchTab;
        window.setDashboardPeriod = setDashboardPeriod;
        window.processarRelatorioTexto = processarRelatorioTexto;
        window.aplicarAoFechamento = aplicarAoFechamento;
        window.limparLeitor = limparLeitor;
        window.salvarFechamento = salvarFechamento;
        window.habilitarEdicaoCaixa = habilitarEdicaoCaixa;
        window.cancelarEdicaoCaixa = cancelarEdicaoCaixa;
        window.setRetiradaFilter = setRetiradaFilter;
        window.salvarRetirada = salvarRetirada;
        window.excluirRetirada = excluirRetirada;
        window.setFiadoFilter = setFiadoFilter;
        window.salvarFiado = salvarFiado;
        window.toggleStatusFiado = toggleStatusFiado;
        window.excluirFiado = excluirFiado;
        window.toggleFiltroInputs = toggleFiltroInputs;
        window.renderizarRelatorioCompleto = renderizarRelatorioCompleto;
        window.renderizarFiados = renderizarFiados;
        window.renderizarRetiradas = renderizarRetiradas;
        window.excluirMovimentacao = excluirMovimentacao;
        window.limparTudo = limparTudo;
        window.exportarCSV = exportarCSV;
        window.closeConfirmModal = closeConfirmModal;
    </script>
</body>
</html>

```
 
