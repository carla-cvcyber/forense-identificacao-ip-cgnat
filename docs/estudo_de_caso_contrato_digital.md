# Estudo de Caso: “O Contrato Assinado de Lugar Nenhum”

## 🎯 Cenário

Um banco digital processa um cliente por inadimplência, alegando que este contratou um empréstimo de R$ 30.000,00 por meio de sua plataforma digital. O banco apresenta como prova um contrato digital assinado, contendo:

* **IP de acesso:** 187.45.102.55
* **Latitude/Longitude:** -23.5505, -46.6333 (São Paulo, SP)
* **Foto (selfie) da biometria facial**
* **Logs do aceite com data e hora:** 10/02/2024, às 14:35

## 👤 Defesa do Cliente

O cliente nega veementemente ter realizado tal contrato, afirmando que estava em viagem no interior, sem acesso à internet, na data do suposto contrato e que nunca teve relação com o dispositivo supostamente usado.

## 🔍 Início da Perícia Judicial

A perícia judicial é iniciada para analisar as provas digitais apresentadas pelo banco.

### 1. Análise da Geolocalização

**Ponto Crucial:** A origem da latitude/longitude (-23.5505, -46.6333) não é devidamente comprovada. O banco não apresenta nenhum log técnico que prove que o dado foi capturado do GPS do dispositivo do cliente, apenas a informação no contrato.

**Questionamento Pericial:** "Essa informação veio da API do celular? De triangulação de antena? De IP? Ou foi manualmente inserida?" Sem a cadeia de custódia da informação, a geolocalização é considerada inválida como prova.

### 2. Investigação do IP

O IP 187.45.102.55 corresponde a um grande provedor de internet (Vivo) e, conforme consulta via MaxMind, indica "São Paulo, SP", o que superficialmente coincide com a geolocalização.

**Alerta Pericial:** Este fato, por si só, não prova que foi o cliente. O IP é dinâmico e, em redes móveis ou CGNAT, pode ser compartilhado por múltiplos usuários.

**Petição ao Juízo:** A perícia recomenda e o juiz determina que o provedor (Vivo) informe quem estava utilizando o IP 187.45.102.55, na **porta lógica 55321**, no dia 10/02/2024 às 14:35.

**Resposta da Vivo:** A operadora informa que o IP é compartilhado por CGNAT e que, **sem a porta lógica, não é possível identificar o cliente específico**.

### 3. Análise da Biometria Facial: Selfie vs. Identificação Biométrica Robusta

A prova apresentada pelo banco era uma **simples "selfie"**, uma imagem estática que, do ponto de vista forense, não pode ser equiparada a uma **amostra biométrica robusta**.

* **Ausência de Metadados e Cadeia de Custódia:** A selfie enviada não possuía **metadados (EXIF)** de origem (como fabricante do dispositivo, data/hora exata da captura, coordenadas GPS ou software de edição). A falta desses dados impede a verificação da originalidade da imagem, levantando a possibilidade de que fosse uma foto preexistente (de redes sociais, por exemplo), uma captura de tela, ou até mesmo uma imagem sintética. Não havia comprovação da **cadeia de custódia** desde a captura no dispositivo do usuário até o sistema do banco.

* **Inexistência de Detecção de Ataque de Apresentação (PAD - Liveness Detection):** O banco não apresentou evidências de que seu sistema realizou qualquer tipo de **teste de vivacidade (liveness detection)**. Sem o PAD, não há garantia de que a imagem foi capturada de uma **pessoa viva em tempo real** no momento da transação, e não de uma foto impressa, uma imagem em tela, uma máscara ou um **deepfake**. O relatório não incluiu:
    * **Logs de processamento do PAD:** Para comprovar a execução do teste.
    * **Resultados do PAD:** Se o teste indicou "vivo" ou "ataque detectado".
    * **Tipo de PAD:** Se era ativo (requerendo ações do usuário como piscar, mover a cabeça) ou passivo (análise de textura, profundidade, reflexos).

* **Falta de Relatório de Validação Biométrica:** Embora o banco mencionasse um fornecedor terceirizado de biometria, não foi apresentado:
    * **Logs de processamento do algoritmo biométrico:** Detalhando como a imagem foi analisada.
    * **Relatório de busca por similaridade:** Que indicasse um **score de correspondência (match score)** entre a selfie e alguma base de dados de referência (como um documento de identidade oficial verificado).
    * **Laudo de validação biométrica:** Atestando a conformidade da identificação com padrões técnicos e forenses.
    * **Base de Comparação:** Não ficou claro contra qual base a selfie foi comparada para "identificar" o cliente.

**Conclusão Pericial sobre a Biometria:** A "selfie" apresentada pelo banco, desprovida de metadados, sem comprovação de vivacidade (PAD) e sem um laudo de validação biométrica com score e base de comparação transparente, é **forensemente insuficiente** para provar a identidade do contratante no momento do aceite. A imagem poderia ter sido obtida de fontes diversas e não há elementos técnicos para garantir sua autenticidade e que representava a pessoa que supostamente realizou o contrato.

## ⚖️ Conclusões Técnicas do Perito

* **Geolocalização:** Não é válida como prova, pois não há cadeia de custódia da informação nem comprovação de que foi capturada do dispositivo da parte. Poderia ter sido inserida manualmente.
* **IP:** Sem a porta lógica, não permite a individualização do usuário. A Vivo confirmou que centenas de usuários compartilhavam o mesmo IP na data/hora informada.
* **Biometria:** A **"selfie" não é uma prova biométrica robusta**. Falhas críticas incluem a ausência de metadados, a falta de comprovação de **vivacidade (PAD)** e a inexistência de um **laudo de validação biométrica** com score e base de comparação transparente, tornando-a imprestável para fins de identificação forense.

## 🏛️ Sentença Judicial

O juiz acolhe integralmente o laudo pericial, fundamentando que a prova digital apresentada pelo banco não é robusta e que a instituição, por não possuir fé pública, não comprovou que o aceite do contrato partiu do cliente.

* **Contrato anulado.**
* **Banco condenado** a pagar danos morais pela negativação indevida e a retirar imediatamente o débito.

---

## 📑 Lições Técnicas e Jurídicas do Caso

| Aspecto           | Erro da Empresa                                                         | Como Deveria Ter Sido Feito                                                                                                                                                                                                                                                                                                                                                                      |
| :---------------- | :---------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Geolocalização** | Inserida sem log técnico, sem prova de origem                           | Usar API de geolocalização do dispositivo, gerar hash dos dados, armazenar logs de captura no backend com cadeia de custódia, incluindo a precisão do GPS e tipo de obtenção (WiFi, célula, GPS).                                                                                                                                                                                             |
| **IP** | Não armazenou porta lógica                                              | Sempre armazenar **IP + porta lógica + data/hora (timestamp)** para correlação robusta com o provedor e individualização em CGNAT. Solicitar e armazenar os logs de NAT do provedor.                                                                                                                                                                                               |
| **Biometria** | Selfie sem metadados, sem validação externa, sem PAD, sem logs de processamento. Sem comparativo com base oficial verificada. | Usar software de biometria certificado que inclua: <br> 1. **Detecção de Ataque de Apresentação (PAD - Liveness Detection)** robusta (ativa ou passiva), com **logs detalhados do resultado do PAD**. <br> 2. Geração de **laudo biométrico** com **score de similaridade**, indicando o nível de confiança da correspondência. <br> 3. Captura de **metadados completos (EXIF)** da imagem/vídeo, incluindo informações do dispositivo, data/hora original e possíveis edições. <br> 4. Comparativo contra **documento de identidade oficial verificado** (RG, CNH) com leitura OCR/MRZ e hash do documento, ou contra template biométrico previamente validado e com cadeia de custódia. <br> 5. **Logs de processamento** detalhados da transação biométrica, incluindo tentativas falhas ou de fraude. |
| **Cadeia de Custódia** | Inexistente                                                             | Implementar política de cadeia de custódia digital rigorosa, com logs auditáveis, hash dos arquivos gerados, e trilha forense íntegra para todas as evidências digitais (IP, localização, biometria, logs de sistema).                                                                                                                                                                             |

## 🚀 Aplicabilidade Forense Real

Este cenário é extremamente comum no Brasil em disputas envolvendo contratos digitais de bancos, financeiras, fintechs e e-commerce. A ausência de uma implementação robusta de cadeia de custódia digital, validação de IP com porta lógica, localização precisa e, fundamentalmente, uma **identificação biométrica que vá além de uma simples "selfie"** e inclua provas de vivacidade e validação forense, leva à criação de contratos digitais sem segurança jurídica, inviabilizando sua validade em juízo.
