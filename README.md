Simulador de Investimentos em Fundos Imobiliários (FIIs)
Projeto desenvolvido para o desafio prático do bootcamp da DIO ministrado pelo Expert Felipe Aguiar.
Este projeto consiste em uma ferramenta interativa desenvolvida em Microsoft Excel com interface inspirada em aplicativos Mobile. A aplicação auxilia investidores na simulação de aportes mensais, estimativa de dividendos passivos e distribuição ideal de carteira por perfil de risco.
A planilha foi criada para responder imediatamente às seguintes perguntas de planejamento financeiro: Quanto investir por mês? Por quantos anos? Qual a taxa de rendimento mensal? Quanto de patrimônio vai acumular? Quanto vai receber de dividendos por mês?

Como as Fórmulas e Técnicas Foram Utilizadas
1. Função VF (Valor Futuro)
A função VF é o motor de cálculo dos juros compostos para os aportes recorrentes.

Fórmula utilizada: =VF(taxa_mensal;prazo_anos*12;-1)

2. Função PROCV com Chave Composta
Para buscar a alocação percentual de cada tipo de fundo de forma dinâmica conforme o perfil selecionado (Conservador,Moderado ou Agressivo):

Chave Composta: Criou-se um identificador único concatenando o Perfil com o Tipo de FII na aba de suporte (ex: Moderado-Papel, Agressivo-Tijolo).

Fórmula: =PROCV(perfil_selecionado & "-" & tipo_fii; TabelaApoio; 3; FALSO)

Intervalos Nomeados Criados

Para tornar as fórmulas legíveis e evitar erros com referências absolutas, foram definidos os seguintes intervalos nomeados no Gerenciador de Nomes do Excel:

"aporte_mensal_calc_rapida" > Célula do aporte mensal na calculadora rápida.
"tempo_de_invest_calc_rapida" > Célula do tempo de investimento na calculadora rápida.
"rendimento_mensal_calc_rapida" > Célula com a taxa de rendimento mensal na calculadora rápida.
"salario" > Célula com o salário do investidor nas configurações de carteira.
"rendimento_medio_carteira" > Célula com a taxa de rendimento médio da carteira.
"aporte_mensal_carteira" > Célula do aporte mensal na carteira.
"perfil_invest" > Célula com a escolha do perfil via Validação de Dados.
"aporte_mensal_perfil_invest" > Célula com o aporte mensal na aba de recomendação por perfil.

Percentuais de Alocação por Perfil de Investidor:

Os percentuais foram estruturados para garantir a diversificação da carteira de acordo com o nível de tolerância ao risco. As % recomendadas para cada perfil de investidor foram baseadas nas recomendações pela IA Gemini do Google de acordo com tipo de fundo imobiliário e do perfil do investidor.

1.Perfil Conservador
Papel: 40%
Tijolo: 10%
Híbrido: 20%
FoFs (Fundos de Fundos): 30%
Desenvolvimento: 0%
Hotelarias: 0%

2.Perfil Moderado
Papel: 25%
Tijolo: 30%
Híbrido: 25%
FoFs (Fundos de Fundos): 15%
Desenvolvimento: 0%
Hotelarias: 5%

3.Perfil Agressivo
Papel: 20%
Tijolo: 30%
Híbrido: 15% 
FoFs (Fundos de Fundos): 5% 
Desenvolvimento: 20%
Hotelarias: 10%

Diferenciais e Evoluções em Relação ao Modelo do Expert:
Nesta versão, foram implementadas as seguintes melhorias para ir além do modelo base:

1.Design Mobile / Layout Vertical: Organização dos blocos operacionais na vertical para facilitar a visualização e navegação fluida em smartphones e dispositivos móveis.
2. Separação de Calculadoras (Rápida vs. Longo Prazo):
Calculadora Rápida: Resposta imediata para tomada de decisão no curto prazo.
Projeções de Longo Prazo utilizam as configurações de carteira para garantir melhor planejamento financeiro: Visão detalhada do patrimônio acumulado para horizontes de 10, 20, 30, 40 e 50 anos.

Como Utilizar:
1. Baixe o arquivo ".xlsx" deste repositório.
2. Abra no Microsoft Excel ou Google Sheets.
3. Insira seu salário, aporte desejado e selecione seu perfil na lista suspensa para ver a mágica acontecer!
