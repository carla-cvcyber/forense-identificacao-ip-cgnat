# Fluxo Pericial: Validação de Identificação por IP

## 🏗️ Etapas Periciais

1. **Coleta dos Dados**
   - Endereço IP
   - Porta lógica
   - Data e horário
   - Logs do provedor (NAT log)
   - Dados do contrato, biometria, geolocalização, etc.

2. **Análise Técnica**
   - Verificar consistência dos dados.
   - Confirmar se há CGNAT no provedor.
   - Validar se os logs permitem individualizar o usuário.

3. **Corroboração com Outras Provas**
   - Geolocalização (ex.: via smartphone, ADB logs).
   - Dados de dispositivo (IMEI, ID de aparelho, número de telefone).
   - Biometria facial ou documental.

4. **Validação de IP**
   - Consultar o provedor de internet para identificar o assinante naquele IP + porta + timestamp.

5. **Geração do Relatório Pericial**
   - Descrever metodologia, achados e limitações.

---

## 🛑 Falhas comuns

- ✔️ IP sem porta lógica = **prova inválida em CGNAT**.
- ✔️ Geolocalização sem prova de origem = questionável.
- ✔️ Ausência de logs do provedor = inviabiliza atribuição.

---