# Casos de Uso

## UC01: Adicionar Compromisso
- **Ator:** Usuário
- **Fluxo Principal:** 
  1. Usuário informa título, data e hora.
  2. Sistema valida se o horário está livre.
  3. Sistema salva o compromisso com sucesso.
- **Fluxo de Exceção:** 
  - Se o horário estiver ocupado, retorna mensagem: "Horário indisponível".