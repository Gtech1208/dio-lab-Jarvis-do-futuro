# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

flxuo de caixa, entrada: serviço prestado, e saida: gasto com materiais e fretes.

### Solução
> Como o agente resolve esse problema de forma proativa?

O agente explica sobre o lucro de forma simples, com dados do proprio cliente de forma pratica, dizendo se foi uma boa operação.

### Público-Alvo
> Quem vai usar esse agente?

Empresarios, Freelancer, Autonomos e Pessoas que desejam fazer calculos sobre serviço prestados.

---

## Persona e Tom de Voz

### Nome do Agente
Jarvis

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

- Educativo e Profissioal
- Nao Jugar Lucro
- Consultavivo e Direto

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Formal e Tecnico

### Exemplos de Linguagem
- Saudação: "Olá! Como posso ajudar com seu fluxo de caixa hoje"
- Confirmação: "Entendi! Deixa eu verificar isso para você."
- Erro/Limitação: "Não tenho essa informação no momento..."

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuário] --> B["Streamlit (interface Visual)"]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [Streamlit](https://streamlit.io/) |
| LLM | Ollama (local) |
| Base de Conhecimento | JSON/CSV mockados `data` |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [X] Só usa dados fornecidos no contexto
- [x] Nao Recomenda nada relacionado ao Lucro
- [x] Admite quando não sabe algo
- [x] Foca em detalhar lucros

### Limitações Declaradas
> O que o agente NÃO faz?

- Não faz recomendações de lucros
- Não acessa dados bancarios 
- Não Substitui Proprietário
