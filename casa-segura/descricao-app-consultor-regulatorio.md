# App Casa Segura: descrição para parecer de enquadramento regulatório

**Versão 1.0 (08/10/2026).** Feita a partir da exportação de todas as telas
da versão publicada (64 telas, gerada em 07/10/2026). Anexo: arquivo HTML
"Casa Segura · todas as telas".

Campos que dependem do responsável estão marcados **[PREENCHER]**. Ligações
entre telas que a exportação não mostra explicitamente estão marcadas
**[CONFIRMAR]**.

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
   material de apoio de um curso educativo? (Ver a seção 8.)
4. Há outros pontos de atenção: CDC, LGPD (dados de saúde de crianças),
   publicidade de saúde e, se aplicável, as normas do conselho profissional
   do responsável?

## 2. Responsável

| Item | Dado |
|---|---|
| Empresa | IJ Vieira Serviços Administrativos (Empresário Individual, ME) |
| CNPJ | 32.438.993/0001-74 |
| Cidade | Jundiaí/SP |
| Contato (consta nos Termos) | israeljvieira@hotmail.com |
| Formação do responsável pelo conteúdo | [PREENCHER: profissão e registro no conselho, se houver] |

## 3. Contexto: o produto em que o app está inserido

O app é uma das ferramentas do **Programa Casa Segura**, um curso online de 3
meses, com aulas gravadas, encontros ao vivo quinzenais e grupo de WhatsApp.
O curso prepara **pais, mães, avós e cuidadores leigos** de crianças de 0 a 5
anos para reagir a imprevistos.

- **Proposta do curso:** ensinar uma sequência de organização, o **Método
  PCS** (Perceber → Classificar → Seguir). O curso não forma profissionais de
  saúde, não emite certificação e não substitui avaliação médica.
- **Comercialização:** R$ 497 pelo programa, com 90 dias de app incluídos.
  Depois disso, o plano "PCS Proteção Contínua" custa R$ 97 por 1 ano ou
  R$ 147 por 2 anos (botão de pagamento ainda desativado).
- **Após o vencimento,** os fluxos de emergência continuam liberados. Apenas
  o histórico de registros depende da renovação.

## 4. Descrição técnica

| Item | Situação atual |
|---|---|
| Tipo | Aplicativo web instalável (PWA), sem loja de aplicativos |
| Endereço | https://casa-segura-beta.vercel.app (hospedagem Vercel) |
| Funcionamento | Offline após o primeiro acesso (cache local) |
| Dados | Só no aparelho (armazenamento local do navegador). Sem servidor próprio, sem cookies de rastreamento, sem análise de comportamento, sem scripts de terceiros |
| Cadastro | Não há conta. Aceite inicial com 3 caixas de seleção e o nome completo do responsável digitado |
| Integrações | Nenhuma (não conecta a sensores, wearables nem outros dispositivos) |
| IA / aprendizado de máquina | Não usa. Lógica fixa, com regras pré-definidas por árvore de decisão |
| Público declarado | Pais, mães ou responsáveis legais de crianças de 0 a 5 anos |

## 5. Finalidade de uso declarada (texto atual do app)

> "O Casa Segura – Matriz do Próximo Passo é uma ferramenta digital de
> orientação educativa para pais e cuidadores de crianças de 0 a 5 anos, em
> situações comuns de urgência doméstica." (Termos de Uso, item 1)

> "O app apresenta perguntas simples e, com base nas suas respostas, indica
> uma orientação inicial: ligar para o serviço de emergência, buscar
> atendimento médico ou observar a criança em casa." (Termos, item 2)

Declarações de limite no app: não faz diagnóstico, não prescreve tratamento
nem indica doses, não é consulta nem telemedicina, não cria relação
médico-paciente e não substitui avaliação presencial (Termos, item 2; aceite
inicial, caixa 1).

## 6. Funcionalidades

### 6.1 Tela inicial

"O que está acontecendo?", com 5 situações: **Convulsão, Febre, Engasgo,
Corte ou ferimento, Queda ou bateu a cabeça.** Também tem os botões "Meus
registros" e "Contatos", e os links "Termos e privacidade" e "Instalar no
celular". A barra fixa **"LIGAR AGORA · 192"** aparece em todas as telas.

### 6.2 Fluxos de decisão (principal ponto de análise)

Cada fluxo faz perguntas sobre sinais observados **na criança** e termina em
uma tela de resultado com cor (semáforo), título, passos numerados, lista de
"NÃO FAÇA", sinais para observar e botões ("Salvar registro", "Agendar
consulta").

**Legenda do app:** 🔴 vermelho = emergência · 🟡 amarelo = atendimento não
urgente · 🟢 verde = observar em casa.

#### Convulsão

| Etapa | Conteúdo |
|---|---|
| Tela inicial (🔴) | "Proteja a criança e marque o tempo". **Cronômetro** com aviso "Se passar de 5 minutos, ligue 192". Passos: deitar de lado, afastar objetos, nada na boca. Não fazer: segurar o corpo, dar algo pela boca, banho frio ou álcool |
| P1 | "A crise passou de 5 minutos, a criança ficou roxa ou não voltou a respirar normalmente?" Sim → 🔴 **"Emergência: chame o SAMU"** (ligar 192, manter de lado, iniciar massagem cardíaca como o 192 orientar) |
| P2 | "É a primeira convulsão da vida dela?" [CONFIRMAR ramificação] |
| P3 | "Ela tem diagnóstico de epilepsia?" Sim → "A crise durou mais que o habitual ou teve crises repetidas sem acordar?" Sim → 🔴 192 · Não → 🟢 **"Siga o plano combinado com o neurologista"** |
| P4 | "Ela estava com febre antes ou durante a crise?" Não → 🔴 **"Convulsão sem febre precisa de investigação"** (ir ao hospital agora) |
| P5 | Checklist: 6 meses a 5 anos, convulsão generalizada, menos de 5 minutos, voltou ao normal rápido. Tudo sim → 🟢 **"Provável convulsão febril simples"** (tratar a febre, consulta em 24 a 48 h) · Algum item falhou → 🟡 **"Leve ao hospital hoje"** |
| Outro resultado | 🟡 "Leve para avaliação hoje" (pronto-socorro nas próximas horas) [CONFIRMAR de qual ramo] |

#### Febre

| Etapa | Conteúdo |
|---|---|
| P1 | Algum destes sinais: não responde ou muito mole, não reage, respira com esforço, manchas roxas que não somem ao apertar? Sim → 🔴 **"Febre com sinal de gravidade"** (192 ou pronto-socorro agora) |
| P2 | "A criança tem menos de 3 meses?" Sim → 🟡 **"Febre em menor de 3 meses precisa de avaliação"** (atendimento hoje) |
| P3 | **Entrada de dados:** data e hora de início da febre (o app **calcula as horas de febre**) e temperatura atual em °C |
| P4 | "Entre os picos, a criança fica ativa, brinca e aceita líquidos?" Não → 🟡 "Leve para avaliação hoje" |
| Resultados por tempo | Mais de 48 h → 🟡 **"Febre há mais de 48 horas"** (agendar consulta) · Até 48 h → 🟢 **"Dá para observar em casa"** (líquidos, roupas leves, antitérmico indicado pelo pediatra na dose do peso) [CONFIRMAR limiar exato] |

#### Engasgo

| Etapa | Conteúdo |
|---|---|
| P1 | "Está tossindo, chorando ou fazendo algum som?" Sim → 🟢 **"Deixe tossir e observe"** (não fazer manobra) |
| P2 | Não → "Qual a idade?" Menos de 1 ano → 🔴 **"Bebê: 5 golpes + 5 compressões"** · 1 ano ou mais → 🔴 **"Manobra de Heimlich"** |
| Botões finais | "Ficou mole e não responde" → 🔴 **"Sem resposta: massagem cardíaca"** (30 compressões e 2 ventilações) · "O objeto saiu e respira" → 🟢 "Continue observando" |

#### Corte ou ferimento

| Etapa | Conteúdo |
|---|---|
| P1 | Sangramento que não para com pressão, osso ou tecido aparente, criança pálida ou sonolenta? Sim → 🔴 **"Pressão contínua e hospital"** |
| P2 | "Onde fica o ferimento?" Articulação, rosto ou perto do olho → 🟡 **"Local de risco: peça avaliação"** · Couro cabeludo → "Foi por queda ou batida?" Sim → leva ao fluxo Queda · Outro lugar → P3 |
| P3 | "Mais de 1 cm, bordas que não se juntam, ou objeto sujo ou enferrujado?" Com **régua na tela** (1, 3 e 5 cm). Não → 🟢 **"Dá para cuidar em casa"** |
| P4 | "A vacina antitetânica está em dia?" Sim → 🟡 **"Provavelmente precisa de sutura"** · Não ou não sei → 🟡 **"Provável sutura e vacina a conferir"** |

#### Queda ou bateu a cabeça

| Etapa | Conteúdo |
|---|---|
| P1 | Não responde, não reage, não mexe um braço ou perna, ou parte do corpo deformada? Sim → 🔴 **"Sinal de alarme após a queda"** (192, não mover, proteger o pescoço) |
| P2 | Perdeu a consciência, teve convulsão, vômitos repetidos, muito sonolenta, pupilas diferentes, sangue ou líquido saindo do nariz ou ouvido? [CONFIRMAR destino: 🔴 ou 🟡] |
| P3 + P4 | Idade (menor de 2 anos / 2 anos ou mais) e altura da queda (4 faixas: até 50 cm, 50 a 90 cm, cerca de 1 m, mais de 1,5 m). Acima do limiar por idade → 🟡 **"Altura de risco: peça avaliação"** |
| P5 | "Depois do choro inicial, voltou ao normal rápido?" Sim → 🟢 **"Observe com atenção por 24 a 48 horas"** · Não → 🟡 **"Comportamento diferente: peça avaliação"** |
| Outro resultado | 🟡 "Algo não está normal: peça avaliação" [CONFIRMAR de qual ramo] |

### 6.3 Telas sem lógica clínica

- **Contatos:** SAMU 192, Disque-Intoxicação 0800 722 6001 e campos para
  cadastrar os telefones do pediatra e do hospital de referência.
- **Meus registros:** data, hora, situação e resultado de cada episódio salvo.
  Fica só no aparelho, com botão "Apagar registros".
- **Agendar consulta:** botão nos resultados amarelos [CONFIRMAR o que faz].
- **Instalar no celular:** instruções para iPhone e Android.
- **Avisos de vigência:** 7 dias antes do fim e após o vencimento.

### 6.4 Textos legais (versão 2026-10-06)

Termos de Uso e Política de Privacidade completos dentro do app, com o botão
"Apagar todos os dados deste aparelho".
- **Base legal para dado de saúde de criança:** consentimento específico do
  responsável no aceite inicial (LGPD, art. 11, I, e art. 14, §1º).
- **Limitação de responsabilidade:** "na máxima extensão permitida pela lei".

## 7. Pontos que o próprio responsável identificou para análise

1. **Títulos de resultado com linguagem diagnóstica.** "Provável convulsão
   febril simples", "Provavelmente precisa de sutura" e "Febre com sinal de
   gravidade" nomeiam uma condição, embora o app declare que "não faz
   diagnóstico". Pedimos orientação sobre a redação.
2. **Processamento de dados da criança.** O fluxo de febre calcula as horas
   de febre a partir da data e hora informadas e usa a idade e a temperatura.
   O fluxo de queda usa a idade e a altura para aplicar um limiar.
3. **Rascunhos em validação clínica:** o texto de RCP no engasgo, os limites
   de altura na queda (0,9 m abaixo de 2 anos; 1,5 m a partir de 2 anos) e a
   conduta para febre entre 24 e 48 horas.

## 8. Versão alternativa a ser avaliada (caminho de menor risco)

Pedimos que o parecer compare a versão atual com esta alternativa:

| Versão atual | Versão alternativa |
|---|---|
| Perguntas sobre a criança → semáforo com conduta para aquele caso | **Fichas de consulta iguais para todos**, com o mesmo conteúdo das aulas ("sinais de alerta na febre", "o que fazer no engasgo") |
| O app escolhe a cor e calcula horas e limiares | O usuário lê os critérios gerais. O app não processa dados da criança |
| Títulos como "Provável convulsão febril simples" | Títulos neutros, sem nomear condição |
| — | Mantém: botão 192, cronômetro, contatos, Plano Familiar de Resposta, registros |

## 9. Material anexado

- [x] Arquivo HTML com todas as telas (64), gerado da versão publicada
- [x] Termos de Uso e Política de Privacidade (dentro do arquivo HTML)
- [x] Texto do aceite inicial (dentro do arquivo HTML)
- [ ] Arquivo da lógica dos fluxos (código), para confirmar as ligações marcadas [CONFIRMAR]
- [ ] Página de venda do programa (quando existir)
- [ ] Cartão CNPJ atualizado
