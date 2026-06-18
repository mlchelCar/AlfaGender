# AlfaGender
Análise de Performance de fundos baseada no gênero do gestor

**Hackathon de Análise de Dados**

## Integrantes

- Caio Nicoluzzi Vieira
- Michel Miskulin
- Marcos Akira Ogasawara
- João Haupt

---

## Tema

O mercado de gestão de fundos de investimento no Brasil é historicamente masculino. Menos de 20% dos gestores registrados na CVM são mulheres. Nossa análise investiga se essa disparidade tem impacto na performance: **fundos geridos por mulheres entregam resultados diferentes dos geridos por homens?**

---

## Dataset

**Fonte:** Portal de Dados Abertos da CVM — [dados.cvm.gov.br](https://dados.cvm.gov.br)

Dois arquivos principais:

- **Cadastro de Fundos** (`cad_fi.csv`) — informações cadastrais de todos os fundos registrados no Brasil, incluindo CNPJ, categoria, situação e nome do gestor responsável
- **Informe Diário** (`inf_diario_fi_YYYYMM.zip`) — dados diários de cada fundo: valor da cota, patrimônio líquido, captações e resgates

Complementar:

- **Classificação de gênero** pelo primeiro nome do gestor via biblioteca `gender-guesser` (Python)
- **Taxa CDI** via API do Banco Central, usada como benchmark

---

## O que faremos

1. Baixar e cruzar o cadastro de fundos com os informes diários
2. Extrair o nome do gestor e classificar gênero (masculino / feminino)
3. Calcular métricas de performance por fundo: retorno acumulado, volatilidade, Sharpe ratio e drawdown máximo
4. Comparar as distribuições entre gestores homens e mulheres, dentro da mesma categoria de fundo
5. Aplicar testes estatísticos (Mann-Whitney) para verificar se as diferenças observadas são significativas
6. Apresentar os resultados com visualizações e uma conclusão sobre a tese
