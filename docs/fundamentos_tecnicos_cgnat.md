# Fundamentos Técnicos: CGNAT e Identificação por IP

## 🔧 O que é CGNAT?

O **Carrier-Grade NAT (CGNAT)** permite que provedores de internet compartilhem um único endereço IP público entre dezenas, centenas ou milhares de clientes, utilizando a técnica de tradução de endereços (NAT) combinada com portas lógicas.

---

## 🔍 Por que IP ≠ Pessoa?

Em ambientes CGNAT:
- ✅ Vários usuários compartilham o mesmo IP público.
- ✅ A diferenciação ocorre pela **porta lógica** atribuída a cada conexão.
- ❌ Um IP isolado não permite identificar individualmente o usuário.

---

## 🗂️ Logs necessários

Para mapear um usuário, é necessário:
- Endereço IP público
- Porta lógica de origem
- Data e horário da conexão
- Logs de NAT do provedor de conexão

---

## 🔗 Funcionamento Simplificado

| IP Público | Porta | Cliente Interno | Timestamp |
|-------------|-------|-----------------|-----------|
| 200.100.50.25 | 58214 | 192.168.0.10 | 2024-05-10 14:32 |
| 200.100.50.25 | 58215 | 192.168.0.20 | 2024-05-10 14:32 |

---

## 🚫 Riscos Periciais

Sem porta e timestamp:
- ❌ Não há como diferenciar usuários.
- ❌ Provas são frágeis e juridicamente contestáveis.

---