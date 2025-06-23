# Perícia Forense: Identificação por IP em Ambientes CGNAT

## 🔍 Sobre este repositório

Este repositório oferece uma referência técnica e jurídica sobre os desafios da identificação de usuários por endereço IP em ambientes onde os provedores utilizam **Carrier-Grade NAT (CGNAT)**.

Inclui:
- 📜 Jurisprudência (Brasil, Austrália, Alemanha, Japão, EUA).
- 🔍 Fluxo pericial para validação de identidade digital via IP.
- 🏛️ Modelos de relatórios periciais e petições judiciais.
- ⚙️ Fundamentos técnicos sobre CGNAT e logs de rede.
- 🧪 **Estudo de caso aprofundado sobre falhas em identificação digital (IP, geolocalização e biometria).**

---

## 🗂️ Conteúdo

- `/docs` – Documentação técnica, fluxo pericial e jurisprudência, **incluindo um estudo de caso detalhado sobre validação de identidade digital.**
- `/templates` – Modelos de relatórios e petições.
- `/diagrams` – Diagramas explicativos (adicione aqui seus próprios arquivos).
- `LICENSE` – Licença do repositório.

---

## ⚠️ Atenção

Endereço IP **não é suficiente para identificar uma pessoa** em ambientes CGNAT. É necessário o conjunto completo:
- ✅ Endereço IP
- ✅ Porta lógica de origem
- ✅ Data e horário (timestamp)
- ✅ Logs do provedor de conexão (NAT log)
- **E, para outras provas digitais como geolocalização e biometria, é fundamental a validação da cadeia de custódia, liveness detection (PAD) e conformidade com padrões forenses.**

---
