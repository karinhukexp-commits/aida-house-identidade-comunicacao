# Como produtos de qualquer plataforma podem aplicar a mesma validação sem dependências ocultas?

O contrato é independente de tecnologia, rede, filesystem externo, credenciais ou motor de IA. Ele especifica entrada e saída que um revisor ou agente implementador pode processar usando exclusivamente o conteúdo empacotado. Não pressupõe que este pacote rode automaticamente como middleware, API ou guardião de produção.

## Entrada canônica

```json
{
  "artifact_id": "conversation-benefits-01",
  "surface": "chat",
  "actor": "aida",
  "audience": "ordinary-user",
  "expressed_need": "Quero saber por onde consulto meus benefícios",
  "context": {"country": "UNKNOWN", "affiliation": "UNKNOWN", "channel": "chat"},
  "candidate": "Veja aqui...",
  "claims": {"action": "none", "authority": "none"},
  "verified_business_facts": [],
  "consent": {"microphone": false, "notifications": false},
  "observed_actions": [],
  "test_evidence": []
}
```

Se dados ausentes, use `UNKNOWN` e prossiga na parte avaliável. Nunca exigir campo não material para revisar. Não enviar dados pessoais só para compor parecer.

## Parecer de saída

```json
{
  "artifact_id": "conversation-benefits-01",
  "communication_status": "AJUSTE_NECESSARIO",
  "factual_status": "FATOS_INSUFICIENTES",
  "runtime_status": "NAO_TESTADO",
  "question": "Como levar a pessoa ao destino aplicável sem pedir nomes de sistemas que desconhece?",
  "user_goal": "Descobrir onde consultar benefícios",
  "plausible_alternative": "Verificar elegibilidade de um benefício específico",
  "considered_questions": ["P01", "P03", "P08"],
  "material_contrasts": ["Fonte encontrada ≠ regra aplicável"],
  "findings": [{"severity": "moderate", "reason": "Destino não confirmado", "suggested_change": "Não inventar link; informar limite e pedir só contexto necessário"}],
  "revised_candidate": "Posso ajudar a encontrar o canal de benefícios para seu contexto. Ainda não tenho um endereço confirmado; para não te indicar o lugar errado, preciso saber o país aplicável.",
  "blocking_issues": [],
  "human_acceptance": "NAO_TESTADO"
}
```

## Decisão editorial e integração

1. `BLOQUEIO_MATERIAL`: não aprovar como comunicação pronta; mostrar motivo e remediação. Ex.: exposição da administração House, consentimento inexistente, ação declarada sem prova.
2. `AJUSTE_NECESSARIO`: produzir redação/fluxo corrigido e reavaliar; não exigir aprovação por rotina.
3. `FATOS_INSUFICIENTES`: responder com limite factual e próximo movimento legítimo, sem declarar inexistência de rota.
4. `APTO_NO_CONTRATO`: pode ser usado como comunicação editorial coerente; não representa certificação do canal ou política empresarial.

Para produção automatizada, quem integra precisa invocar o validador, alimentar evidências, respeitar bloqueios e demonstrar funcionamento. A skill não inspeciona automaticamente todo software, não aplica mudança de código e não autoriza publicação. Quando não há integração, fornecer protocolo de validação manual/assistida com a mesma entrada/saída.
