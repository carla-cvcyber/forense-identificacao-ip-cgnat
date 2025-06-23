# Modelo de Relatório Pericial – Identificação por IP em CGNAT

## 1. Introdução
Descreve o objetivo da perícia e o contexto do litígio.

---

## 2. Metodologia Técnica
- Análise de logs de IP, porta e timestamp.
- Verificação do uso de CGNAT.
- Consulta ao provedor de conexão.
- Corroboração com outras provas digitais (geolocalização, **biometria facial**, logs de sistemas).

---

## 3. Análise dos Dados
- Dados fornecidos (IP, Porta, Timestamp, **informações de geolocalização e biometria, se aplicável**).
- Existência ou não de correlação confiável entre os dados.
- Avaliação da robustez de outras provas digitais, como geolocalização e **biometria (incluindo liveness detection, metadados e laudos de validação)**, sob a ótica da cadeia de custódia e padrões forenses.

---

## 4. Estudo de Caso Relevante
Para ilustrar a aplicação prática das metodologias e conclusões, consulte o **Estudo de Caso: “O Contrato Assinado de Lugar Nenhum”** detalhado em [./estudo_de_caso_contrato_digital.md](./estudo_de_caso_contrato_digital.md). Este caso demonstra as falhas comuns em provas digitais (IP sem porta, geolocalização sem custódia, e **biometria sem validação forense e liveness detection**) e suas implicações jurídicas.

---

## 5. Conclusão
- Se os dados permitem ou não a atribuição segura do usuário.
- Limitações técnicas identificadas, como ausência de logs completos, uso de CGNAT sem porta, ou falhas na cadeia de custódia de outras provas digitais, **incluindo a ausência de PAD (liveness detection), metadados ou laudos de validação biométrica**.
- Recomendações para a validação futura de provas digitais.
