# Modelo de Relatório Pericial

## Dados do Processo:
- Processo nº: [Número]
- Vara: [Vara]
- Autor: [Nome]
- Réu: [Nome]

---

## 1. Objeto da Perícia
Analisar se é possível associar a conexão de IP [xxx.xxx.xxx.xxx] (e, se disponível, porta lógica [yyyyy] e timestamp [dd/mm/aaaa hh:mm]) ao usuário identificado no processo, e avaliar a robustez de outras provas digitais **como geolocalização e biometria facial, se aplicáveis**.

---

## 2. Metodologia
- Análise de logs de rede, incluindo IP, porta lógica e timestamp.
- Verificação da presença de CGNAT no provedor de conexão.
- Eventual consulta ao provedor de internet para obtenção de logs de NAT.
- Avaliação da cadeia de custódia e integridade de quaisquer outras provas digitais (geolocalização, **biometria facial, etc.**).
- **Análise da evidência biométrica para verificar a presença de Detecção de Ataque de Apresentação (PAD - Liveness Detection), metadados e aderência a padrões forenses de identificação.**
- Comparação com padrões técnicos e forenses para validação de identidade digital.

---

## 3. Análise Técnica
- **Dados analisados:** [Descrever todos os dados e provas digitais fornecidos para análise, ex: IP, porta, timestamp, coordenadas GPS, selfie, logs de sistema.]
- **Análise do IP:** [Descrever se o IP possui porta lógica associada, se o provedor usa CGNAT, e se os dados do provedor foram obtidos. Analisar a capacidade de individualização do usuário com base no IP e porta.]
- **Análise da Geolocalização:** [Descrever a origem informada da geolocalização e avaliar se há logs ou evidências que comprovem sua cadeia de custódia e que ela foi capturada diretamente do dispositivo do usuário. Indicar a precisão da coordenada, se disponível.]
- **Análise da Biometria Facial:** [Descrever a forma como a biometria foi apresentada (ex: selfie, vídeo), e detalhar a ausência ou presença dos seguintes elementos críticos:
    * **Metadados (EXIF) da imagem/vídeo:** [Indicar se presentes e o que revelam (dispositivo, data/hora, manipulação).]
    * **Detecção de Ataque de Apresentação (PAD - Liveness Detection):** [Indicar se o sistema utilizado forneceu logs ou resultados de PAD. Discutir se o teste era ativo ou passivo e sua robustez. Se ausente, indicar que não há prova de que a imagem veio de uma pessoa viva em tempo real.]
    * **Laudo de Validação Biométrica:** [Indicar se o banco forneceu um laudo com score de similaridade, tipo de algoritmo e base de comparação (ex: RG, CNH). Se ausente, indicar a impossibilidade de verificar a correspondência de forma forense.]
    * **Logs de Processamento da Biometria:** [Indicar se há logs detalhados do processo de captura e validação biométrica.]
    * **Cadeia de Custódia da Amostra Biométrica:** [Avaliar como a amostra foi coletada e mantida íntegra.]
    * **Conclusão sobre a robustez da prova biométrica.**]
- **Correlação das Provas:** [Analisar se o conjunto de provas digitais (IP, geolocalização, biometria) se correlaciona de forma consistente e robusta para atribuir a ação ao usuário. Destacar quaisquer inconsistências ou falhas que comprometam a atribuição.]

---

## 4. Conclusão
- **É possível atribuir tecnicamente a ação ao usuário?** [Indicar claramente se é possível ou não, com base na análise do conjunto probatório.]
- **Limitações:** [Se não for possível, apontar todas as limitações identificadas, como: ausência de porta lógica para o IP em ambiente CGNAT, falta de cadeia de custódia da geolocalização, **ausência de liveness detection (PAD), metadados ou laudos de validação biométrica para a prova de identidade**, ou qualquer outra falha na prova digital que comprometa sua integridade ou validade. Referenciar as lições do Estudo de Caso "O Contrato Assinado de Lugar Nenhum" para contextualização, se pertinente.]

---

Assinatura:  
Perito Judicial – Carla Vieira

