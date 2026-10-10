# 🏢 Simulador de Investimentos em Fundos Imobiliários

## 🎯 O que é este projeto?
Esta é uma ferramenta desenvolvida no Excel para simular o crescimento do patrimônio e a geração de renda passiva (dividendos) através de Fundos Imobiliários (FIIs). O simulador projeta cenários de longo prazo e divide a carteira de acordo com o perfil do investidor.

A planilha responde diretamente a cinco perguntas de negócio fundamentais:
1. **Quanto investir por mês?** (Definido no input de Aporte Mensal)
2. **Por quantos anos?** (Definido no input de Prazo)
3. **Qual a taxa de rendimento mensal?** (Definido no input de Taxa)
4. **Quanto de patrimônio vai acumular?** (Calculado automaticamente usando a função VF)
5. **Quanto vai receber de dividendos por mês?** (Calculado sobre o patrimônio final)

## 🧮 Como os cálculos funcionam por dentro
### Função VF (Valor Futuro)
Utilizada para calcular o efeito dos juros compostos ao longo do tempo. 
A fórmula aplicada foi: `=VF(taxa_mensal; prazo_anos * 12; -aporte_mensal; 0; 0)`. 
*Nota: O aporte entra negativo na fórmula pois para o Excel ele representa uma "saída" de caixa (dinheiro saindo do bolso para o investimento).*

### Função PROCV
Utilizada para distribuir automaticamente o aporte mensal entre diferentes tipos de fundos com base no perfil selecionado. 
A fórmula busca o percentual correspondente na aba de apoio e multiplica pelo aporte: 
`=aporte_mensal * PROCV(perfil_escolhido; Tabela_Apoio!A:G; num_coluna; FALSO)`.

## 🏷️ Intervalos Nomeados (Name Manager)
Para manter as fórmulas limpas, legíveis e evitar erros de referência, criei os seguintes intervalos nomeados:
- `aporte_mensal`: Célula que recebe o valor do aporte.
- `taxa_mensal`: Célula com a expectativa de rendimento.
- `prazo_anos`: Célula com o tempo de investimento.
- `perfil_escolhido`: Célula com a validação de dados (lista suspensa) do perfil.

## 📊 Distribuição da Carteira (Perfis de Investidor)
Criei uma aba de apoio oculta com percentuais definidos para 6 tipos de fundos imobiliários:
- **Conservador:** 40% Papel | 20% Tijolo | 10% Fiagro | 10% FoF | 10% Logística | 10% Shopping
- **Moderado:** 25% Papel | 25% Tijolo | 15% Fiagro | 15% FoF | 10% Logística | 10% Shopping
- **Arrojado:** 10% Papel | 30% Tijolo | 20% Fiagro | 15% FoF | 15% Logística | 10% Shopping
*(Os percentuais foram criados para fins de simulação e somam 100% em todos os cenários).*

## 🚀 Evoluções e Diferenciais (Melhorias aplicadas)
- Implementação de 6 categorias de fundos imobiliários, ampliando a diversificação.
- Painel formatado com cores institucionais e células de cálculo bloqueadas visualmente em cinza.
- Ocultação das linhas de grade, títulos e barra de fórmulas para dar ao Excel uma verdadeira "cara de aplicativo".
- Projeção de cenários automatizada com referências relativas e absolutas.

## 📸 Demonstração Visual
<img width="1283" height="596" alt="Captura de tela 2026-10-10 194348" src="https://github.com/user-attachments/assets/66ed0a79-8a08-4827-9b8a-b2ac4a9ca45f" />

