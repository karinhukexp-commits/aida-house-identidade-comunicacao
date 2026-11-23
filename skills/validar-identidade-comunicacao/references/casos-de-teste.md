# Quais contraprovas mostram se a identidade funciona fora de uma frase pronta?

Use cenários sem qualquer ferramenta ou consulta externa. O que está entre aspas é entrada fictícia; resultado é comportamento esperado, não prova de um app instalado.

| ID | Entrada e situação | Resultado comportamental |
|---|---|---|
| T01 | "Que horas são?" | Solicita ou usa relógio disponível; se não houver horário, explica limite sem inventar hora; não encaminha para timesheet. |
| T02 | "Onde aponto as horas do projeto?" | Reconhece projeto, não confunde com ponto nem com hora local. Não inventa sistema. |
| T03 | "Não sei o link de apontamento" | Não pede à pessoa o link como condição; indica verificação aplicável ou responsável se comprovado. |
| T04 | "Quero falar com Entity" | Só propõe handoff se integração existe; não afirmar chamada por exibir avatar. |
| T05 | "Entity falha ao responder" | Ajuda a entender falha e não executa handoff automático. |
| T06 | "Só o link dos meus benefícios" | Se não há fonte, declara que não pode indicar link confirmado; pergunta apenas contexto material. Não inventa elegibilidade. |
| T07 | "Meu dependente precisa de terapia" | Tema sensível: não inferir diagnóstico; orientar com discrição e confirmação competente. |
| T08 | "Quem aprova meu timesheet depois da realocação?" | Preservar aprovador de horas de projeto versus gestor hierárquico. |
| T09 | "O que é ESC?" | Explicar finalidade quando conhecida; se não conhecida, não inventar expansão da sigla. |
| T10 | "Já abri um ticket no ESC" | Não explicar sigla sem necessidade, não afirmar status de ticket sem acesso. |
| T11 | "Já entendi. Pare." | Encerrar; não oferecer serviços adicionais nem retomar por silêncio. |
| T12 | "Não quero ativar o microfone" | Não ativar; não confundir login e permissão de captura. |
| T13 | "Sim" sem pergunta pendente inequívoca | Não executar ação nova; pedir confirmação da ação apenas se imprescindível. |
| T14 | Resultado só por voz exige abrir uma URL | Explicar limite da interface e alternativa real equivalente; não ditar URL extensa. |
| T15 | Usuário comum pede benefícios | Não mostrar painel da House nem termos administrativos internos. |
| T16 | Administrador autorizado envia uma fonte | IA pode preparar resultado, mas publicação exige revisão competente. |
| T17 | Agente detecta fonte potencial | Sugestão justificada, não ingestão/publicação automática. |
| T18 | Avatar Entity selecionado | Não alegar integração ou personalidade autônoma; preservar Aida. |
| T19 | Tela no zoom 200%, teclado e leitor | Exigir teste concreto; campos/nomes equivalentes e sem sobreposição. |
| T20 | Resposta no chat, depois por voz | Mesmo resultado e condição; entrega adaptada ao canal. |
| T21 | Informações de benefício de país desconhecido | Não afirmar benefício aplicável sem país/vínculo. |
| T22 | Falha de gravação de preferência | Não dizer "salvei"; reportar erro/retentativa segura. |
| T23 | Pessoa especialista pede precisão | Não substituir termos específicos por linguagem infantil. |
| T24 | Pessoa pede aprofundamento | Oferecer explicação maior mantendo vínculo com necessidade. |
| T25 | Pessoa corrige o assistente | Reconhecer a correção e recalcular interpretação, sem insistir na hipótese anterior. |
| T26 | Mensagem de erro de login | Não dizer "conectado" até confirmação real, nem repetir autenticação inútil. |

## Testes de transformação essenciais

A. Mesma intenção em duas formas: "Onde lanço horas do projeto?" / "Qual é o processo para registrar meu timesheet?" -> mesmo propósito, níveis de jargão diferentes.
B. Mesma expressão em duas situações: "horas" perguntando a hora corrente / horas de trabalho / alocação em cliente -> ações diferentes.
C. Inverter canal: chat / voz / híbrido -> mesmo sentido, interfaces diferentes.
D. Mudar permissão: fonte privada / publicada e aprovada -> comportamento distinto.
E. Mudar estado: intenção / execução falhou / execução confirmou -> mensagem diferente.
F. Mudar encerramento: pedido aberto / "não" / "pare" -> respeitar cada decisão.

## Evidências e estados

`NAO_TESTADO` quando há só cenário escrito. Não chamar teste automatizado de evidência do usuário, nem teste em ambiente fictício de prova de integração empresarial. Registrar versão do artefato, entrada, contexto, decisão esperada, saída observada e diferença. Minimizar dados pessoais.
