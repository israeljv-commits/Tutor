# App Casa Segura: descrição para parecer de enquadramento regulatório

**Rascunho v0.1 (07/10/2026).** Feito a partir do relatório de desenvolvimento.
Os campos marcados **[PREENCHER]** serão completados com as telas e os textos
reais do app.

---

## 1. Solicitação ao consultor

Pedimos um **parecer por escrito** respondendo:

1. O app Casa Segura, na versão descrita abaixo, se enquadra como software
   como dispositivo médico (SaMD) nos termos da RDC 657/2022 e da RDC
   751/2022?
2. Se sim: qual a classe de risco provável e qual o regime (notificação ou
   registro)? O que a empresa precisaria (AFE, responsável técnico, Boas
   Práticas de Fabricação, documentação técnica), com estimativa de prazo e
   custo?
3. Que alterações de funcionalidade, texto ou finalidade de uso deixariam o
   app **fora** do escopo de regularização, mantendo sua utilidade como
   material de apoio de um curso educativo?
4. Há outros pontos de atenção: CDC, LGPD, publicidade de saúde e, se
   aplicável, as normas do conselho profissional do responsável?

## 2. Responsável

| Item | Dado |
|---|---|
| Empresa | IJ Vieira Serviços Administrativos (Empresário Individual, ME) |
| CNPJ | 32.438.993/0001-74 |
| Cidade | Jundiaí/SP |
| Contato | [PREENCHER: e-mail oficial] |
| Formação do responsável pelo conteúdo | [PREENCHER: profissão e registro no conselho, se houver] |

## 3. Contexto: o produto em que o app está inserido

O app é uma das ferramentas do **Programa Casa Segura**, um curso online de 3
meses, com aulas gravadas, encontros ao vivo quinzenais e grupo de WhatsApp.
O programa prepara **pais, mães, avós e cuidadores leigos** para reagir a
imprevistos com crianças.

- **Proposta declarada:** ensinar uma sequência de organização, o **Método
  PCS** (Perceber → Classificar → Seguir). O programa não forma
  profissionais de saúde, não emite certificação e não substitui avaliação
  médica.
- **Comercialização:** R$ 497 pelo programa (90 dias de app incluídos).
  Renovação opcional do app por R$ 97 (1 ano) ou R$ 147 (2 anos).
- **Público excluído explicitamente:** profissionais que buscam formação
  clínica e pessoas que procuram diagnóstico pela internet.

## 4. Descrição técnica

| Item | Situação atual |
|---|---|
| Tipo | Aplicativo web instalável (PWA), sem loja de aplicativos |
| Endereço | https://casa-segura-beta.vercel.app (hospedagem Vercel) |
| Funcionamento | Offline após o primeiro acesso |
| Dados | Ficam só no aparelho do usuário. Sem servidor, sem cookies, sem rastreadores |
| Cadastro | Não há conta. Há uma tela de aceite com 3 caixas e o nome completo digitado |
| Integrações | Nenhuma. Não conecta a sensores, wearables ou outros dispositivos |
| IA / aprendizado de máquina | Não usa. A lógica é fixa, com regras pré-definidas [CONFIRMAR] |

## 5. Funcionalidades

### 5.1 Fluxos por situação (núcleo do app, **principal ponto de análise**)

Cinco situações: **convulsão, febre, engasgo, corte ou ferimento, queda ou
batida na cabeça**.

Funcionamento atual: o usuário escolhe a situação e responde a perguntas
sobre os sinais que observa na criança, uma decisão por tela. Ao fim, o app
mostra um **semáforo** com a orientação de próximo passo:

- 🔴 **Vermelho:** ligar 192 / procurar atendimento imediato
- 🟡 **Amarelo:** [PREENCHER: texto exato, por exemplo "procurar atendimento em X horas"]
- 🟢 **Verde:** [PREENCHER: texto exato, por exemplo "observar em casa e consultar o pediatra"]

Recursos de apoio dentro dos fluxos:
- **Corte:** régua de 1, 3 e 5 cm na tela, para estimar o tamanho do ferimento.
- **Convulsão:** cronômetro de 5 minutos.
- **Febre:** cálculo de quantas horas a febre já dura.
- **Queda:** critério de altura (0,9 m abaixo de 2 anos; 1,5 m a partir de
  2 anos). Rascunho ainda pendente de validação clínica.
- **Engasgo:** texto de RCP. Rascunho ainda pendente de validação clínica.

[PREENCHER: para cada fluxo, a lista de perguntas e quais respostas levam a
qual cor. Ideal: print de cada tela ou exportação do arquivo de fluxos.]

### 5.2 Barra fixa "LIGAR AGORA · 192"

Visível em todas as telas e liga direto para o SAMU.

### 5.3 Telas de organização familiar (sem lógica clínica)

- **Contatos:** pediatra, familiares, plano de saúde.
- **Registros:** anotações do usuário sobre episódios (data, hora, o que
  aconteceu).
- **Agendar consulta:** atalho para marcar consulta [CONFIRMAR o que faz].
- **Instruções de instalação.**

### 5.4 Textos legais

- Termos de Uso e Política de Privacidade (LGPD) dentro do app.
- Botão "Apagar todos os dados deste aparelho".
- O app usa a palavra **"orientação"** e declara não substituir avaliação
  profissional [PREENCHER: copiar a frase exata].

### 5.5 Vigência

O acesso conta 90 dias a partir do primeiro aceite e avisa 7 dias antes de
vencer. **Depois do vencimento, os fluxos de emergência continuam
liberados**; só o histórico e os registros dependem de renovação.

## 6. Finalidade de uso declarada

> [PREENCHER com o texto exato do app e da página de venda.]
> Proposta: "Material de apoio do Programa Casa Segura para organizar a
> observação e lembrar a sequência ensinada no curso. Não realiza diagnóstico
> nem substitui avaliação de profissional de saúde. Em emergência, ligue 192."

## 7. Versão alternativa a ser avaliada (caminho de menor risco)

Pedimos que o parecer compare a versão atual com esta alternativa:

| Versão atual | Versão alternativa |
|---|---|
| Perguntas sobre os sinais **da criança** → semáforo com conduta para aquele caso | Fichas de consulta **iguais para todos**: "sinais de alerta de febre", "o que fazer no engasgo", com o mesmo conteúdo das aulas |
| O app "decide" a cor | O usuário lê os critérios gerais; o app não processa dados da criança |
| — | Mantém: botão 192, cronômetro, contatos, Plano Familiar de Resposta, registros |

## 8. Material que será anexado

- [ ] Prints de todas as telas (os 5 fluxos completos, com cada resultado)
- [ ] Arquivo com a lógica dos fluxos (perguntas → resultados)
- [ ] Termos de Uso e Política de Privacidade
- [ ] Texto da tela de aceite
- [ ] Página de venda do programa (quando existir)
- [ ] Cartão CNPJ atualizado
