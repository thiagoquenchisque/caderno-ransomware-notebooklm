# Análise Comparativa de Fontes sobre Ransomware

Este documento apresenta uma análise comparativa de 12 fontes sobre ransomware, selecionadas para subsidiar o desenvolvimento de um caderno temático em Segurança da Informação.

## 1. Tabela Comparativa das Fontes

| # | Fonte | Autor / Instituição | Ano | Tipo de Fonte | Principais Assuntos | Contribuição para o Estudo | Relevância |
|---|---|---|---|---|---|---|---|
| 1 | 15 Exemplos de Ataques de Ransomware Recentes — Trend Micro | Joe Lee / Trend Micro | 2025 | Artigo informativo/técnico | Ransomware-as-a-Service (RaaS) e análise de 15 grupos, incluindo RansomHub, Rhysida, Akira, WannaCry, LockBit, BlackCat e Hive | Apresenta um panorama prático das táticas, técnicas e formas de infecção utilizadas por grupos criminosos, incluindo phishing e Cobalt Strike. | Alta |
| 2 | 7 Types of Ransomware Attacks in 2026 — SentinelOne | SentinelOne | 2026 | Artigo técnico educativo | Classificação em sete tipos: Crypto, Locker, Scareware, Doxware, RaaS, Double Extortion e Fileless | Apresenta uma classificação atualizada das principais modalidades de ransomware e destaca técnicas modernas, como dupla extorsão e ataques fileless. | Alta |
| 3 | A diferença entre ransomware e malware — Check Point | Check Point Software Technologies | Não informado | Artigo técnico explicativo | Diferenças entre malware e ransomware, criptografia, ransomware híbrido, worms, roubo de dados e wipers | Facilita a compreensão conceitual entre malware e ransomware e apresenta comportamentos destrutivos, como os observados no NotPetya. | Alta |
| 4 | Como evitar ransomware — 9 dicas — Fortinet | Fortinet | Não informado | Guia prático/educativo | Prevenção, firewalls, backups, VPN, conscientização e resposta a incidentes | Fornece orientações práticas para prevenção, contenção e recuperação após incidentes de ransomware. | Alta |
| 5 | Como se proteger de ransomware — Kaspersky | Kaspersky | Não informado | Artigo corporativo | Vulnerabilidades, prevenção, antivírus, backups e conscientização | Destaca vulnerabilidades comuns e a importância de backups confiáveis e da conscientização dos colaboradores. | Média |
| 6 | Exemples de Ransomware: 15 Attaques de Ransomware — CrowdStrike | Erik Episcopo / CrowdStrike | 2022 | Artigo técnico/histórico | Histórico e funcionamento de 15 variantes, incluindo CryptoLocker, DarkSide, Dharma, GandCrab, Maze, NotPetya, REvil, Ryuk, SamSam e WannaCry | Contribui para a compreensão da evolução histórica do ransomware e da formação do atual ecossistema cibercriminoso. | Alta |
| 7 | O que é ransomware? Como evitar ataques de ransomware? — Fortinet | Fortinet | Não informado | Artigo conceitual | Definição, história, formas de infecção, malspam, malvertising, tipos de ransomware e honeypots | Oferece contexto histórico, conceitos fundamentais e técnicas de detecção e prevenção. | Alta |
| 8 | O que é ransomware? — IBM | Matthew Kosinski / IBM Think | Não informado | Artigo técnico de referência | Extorsão dupla e tripla, vetores de infecção, RaaS, ciclo de vida do ataque e evolução histórica | É uma das fontes mais abrangentes, apresentando uma estrutura organizada do ciclo de vida de um ataque e conceitos modernos de ransomware. | Alta |
| 9 | Proteção contra ransomware: 5 estratégias indispensáveis — Tempest | Tempest | 2024 | Guia estratégico corporativo | Backups, patches, vulnerabilidades, endpoints, resposta a incidentes e segmentação de rede | Destaca medidas de segurança corporativa, especialmente segmentação de rede, monitoramento e resposta a incidentes. | Alta |
| 10 | Ransomware explicado: O que é ransomware e como se proteger? — Kaspersky | Kaspersky | Não informado | Guia de referência | Conceitos, funcionamento, WannaCry, Maze, double/triple extortion, sinais de infecção e backup 3-2-1 | Possui forte caráter didático e apresenta estratégias de prevenção, identificação de infecção e recuperação de dados. | Alta |
| 11 | Search — ENISA | European Union Agency for Cybersecurity | 2026 | Índice de publicações | Secure by Design, Cyber Resilience Act (CRA), segurança em hospitais e maturidade de PMEs | Contribui principalmente para o entendimento de políticas públicas, regulamentações e estratégias de resiliência cibernética. | Média/Baixa |
| 12 | Was ist Ransomware? — CrowdStrike | Kurt Baker / CrowdStrike | 2022 | Artigo técnico educativo | Funcionamento, estatísticas, fator humano, pagamento de resgate, prevenção e contenção | Apresenta dados históricos e orientações detalhadas para contenção de infecções, incluindo isolamento de dispositivos e redes. | Alta |

## 2. Fontes Recomendadas como Referências Principais

A partir da análise das 12 fontes, foram selecionadas quatro referências principais para servirem como pilares do caderno temático.

### 2.1 IBM — O que é ransomware?

Autor: Matthew Kosinski / IBM Think

Relevância: Alta

A fonte apresenta uma estrutura abrangente para compreender o funcionamento de um ataque de ransomware, organizando-o em diferentes etapas:

1. Acesso inicial
2. Pós-exploração
3. Expansão dentro do ambiente
4. Coleta e exfiltração de dados
5. Implementação do ransomware e envio da nota de resgate

Além disso, aborda conceitos contemporâneos, como:

- Ransomware-as-a-Service (RaaS);
- Dupla extorsão;
- Tripla extorsão;
- Vetores de infecção;
- Impactos financeiros;
- Evolução histórica do ransomware.

Principal contribuição: fundamentação teórica e compreensão do ciclo de vida de um ataque.

### 2.2 Kaspersky — Ransomware explicado

Instituição: Kaspersky

Relevância: Alta

A fonte apresenta uma abordagem didática sobre ransomware, sendo especialmente adequada para a introdução aos conceitos fundamentais.

Entre os principais conteúdos estão:

- Diferença entre ransomware e vírus;
- Funcionamento de um ataque;
- Principais formas de acesso utilizadas pelos criminosos;
- Exemplos como WannaCry e Maze;
- Double Extortion e Triple Extortion;
- Sinais de uma possível infecção;
- Estratégias de prevenção;
- Regra de backup 3-2-1;
- Orientações para resposta a incidentes.

Principal contribuição: conceitos fundamentais, conscientização dos usuários, prevenção e estratégia de backup.

### 2.3 Fortinet — Como evitar ransomware

Instituição: Fortinet

Relevância: Alta

A fonte é especialmente útil para as partes do caderno relacionadas à prevenção, mitigação e resposta a incidentes.

O material apresenta um fluxo operacional que pode ser sintetizado em:

Isolar → Identificar → Remover → Recuperar → Avaliar o pagamento do resgate

Também aborda mecanismos e práticas de proteção, como:

- Firewalls;
- Backups;
- VPNs;
- Conscientização dos usuários;
- Segurança da infraestrutura;
- Planos de resposta a incidentes;
- Recuperação de dados.

Principal contribuição: aplicação prática dos conceitos de prevenção e resposta a ataques de ransomware.

### 2.4 CrowdStrike — 15 ataques de ransomware

Autor: Erik Episcopo / CrowdStrike

Ano: 2022

Relevância: Alta

A fonte fornece importante contexto histórico ao apresentar diferentes famílias e grupos de ransomware.

Entre os exemplos analisados estão:

- CryptoLocker;
- NotPetya;
- WannaCry;
- SamSam;
- Ryuk;
- REvil;
- Maze;
- DarkSide;
- GandCrab.

O conteúdo permite observar como diferentes técnicas, famílias e modelos de negócio contribuíram para a evolução do ransomware, principalmente a partir da década de 2010.

Principal contribuição: contexto histórico e estudos de caso.

## 3. Síntese da Seleção

| Fonte | Principal Utilidade no Caderno |
|---|---|
| IBM | Fundamentação teórica e ciclo de vida dos ataques |
| Kaspersky | Conceitos, conscientização, prevenção e backups |
| Fortinet | Mitigação, prevenção e resposta a incidentes |
| CrowdStrike | História, evolução e estudos de caso |

A combinação dessas quatro fontes permite abordar o ransomware de maneira teórica, histórica e prática, evitando que o estudo fique concentrado em apenas uma perspectiva.

## 4. Estrutura Sugerida para o Caderno Temático

### 4.1 Introdução

- O que é Segurança da Informação;
- O que é ransomware;
- Por que ransomware representa uma ameaça relevante;
- Objetivos do caderno temático.

### 4.2 Conceitos Fundamentais

- Malware;
- Ransomware;
- Vírus, worms e trojans;
- Criptografia;
- Extorsão digital;
- Ransomware-as-a-Service (RaaS).

### 4.3 Evolução Histórica do Ransomware

- AIDS Trojan;
- CryptoLocker;
- WannaCry;
- NotPetya;
- Ryuk;
- REvil;
- Maze;
- DarkSide;
- Grupos modernos de ransomware.

### 4.4 Funcionamento de um Ataque

- Acesso inicial;
- Exploração de vulnerabilidades;
- Persistência;
- Movimentação lateral;
- Escalada de privilégios;
- Coleta de informações;
- Exfiltração de dados;
- Criptografia;
- Extorsão;
- Nota de resgate.

### 4.5 Principais Tipos de Ransomware

- Crypto ransomware;
- Locker ransomware;
- Scareware;
- Doxware;
- Ransomware-as-a-Service;
- Double Extortion;
- Triple Extortion;
- Fileless ransomware.

### 4.6 Principais Vetores de Infecção

- Phishing;
- Malspam;
- Malvertising;
- Exploração de vulnerabilidades;
- Credenciais comprometidas;
- Serviços expostos à Internet;
- Downloads maliciosos;
- Engenharia social.

### 4.7 Impactos dos Ataques

- Perda de dados;
- Interrupção de serviços;
- Prejuízos financeiros;
- Vazamento de informações;
- Danos à reputação;
- Impactos operacionais;
- Consequências legais e regulatórias.

### 4.8 Prevenção

- Backups;
- Regra 3-2-1;
- Atualização e aplicação de patches;
- Gestão de vulnerabilidades;
- Antivírus e EDR;
- Firewalls;
- Segmentação de rede;
- Autenticação multifator;
- Treinamento e conscientização;
- Princípio do menor privilégio.

### 4.9 Resposta a Incidentes

Um fluxo básico de resposta pode ser representado como:

Detecção  
↓  
Isolamento  
↓  
Identificação  
↓  
Contenção  
↓  
Erradicação  
↓  
Recuperação  
↓  
Monitoramento  
↓  
Lições aprendidas

### 4.10 Estudos de Caso

Sugestões de casos para análise:

- CryptoLocker;
- WannaCry;
- NotPetya;
- Ryuk;
- REvil;
- Maze;
- DarkSide.

Para cada caso, recomenda-se analisar:

- Ano;
- Grupo ou família;
- Vetor de entrada;
- Técnica utilizada;
- Impacto;
- Forma de extorsão;
- Consequências;
- Medidas de prevenção aplicáveis.

### 4.11 Conclusão

A conclusão deverá sintetizar:

- A evolução do ransomware;
- A profissionalização do cibercrime;
- A importância do RaaS;
- A necessidade de prevenção;
- A importância dos backups;
- A necessidade de planos de resposta a incidentes;
- O papel da conscientização dos usuários.

## 5. Conclusão da Análise das Fontes

A análise das 12 fontes demonstra que o ransomware deve ser estudado de forma multidimensional, considerando tanto seus aspectos técnicos quanto históricos, organizacionais e humanos.

As fontes selecionadas apresentam diferentes perspectivas:

- IBM: estrutura teórica e ciclo de vida;
- Kaspersky: conceitos, prevenção e conscientização;
- Fortinet: resposta e mitigação;
- CrowdStrike: evolução histórica e estudos de caso;
- Trend Micro e SentinelOne: ameaças e técnicas mais recentes;
- Tempest: segurança corporativa e resiliência;
- ENISA: políticas públicas e regulamentação.

Dessa forma, a utilização conjunta das fontes permite construir um caderno temático consistente, capaz de explicar o que é ransomware, como os ataques funcionam, como evoluíram, quais são seus impactos e quais medidas podem ser utilizadas para prevenção e resposta.

## 6. Referências Principais

As quatro fontes consideradas prioritárias para o desenvolvimento do trabalho são:

1. IBM — O que é ransomware?
2. Kaspersky — Ransomware explicado: O que é ransomware e como se proteger?
3. Fortinet — Como evitar ransomware: 9 dicas
4. CrowdStrike — Exemples de Ransomware: 15 Attaques de Ransomware

> Observação: antes da entrega final do projeto, recomenda-se conferir os dados bibliográficos diretamente nas páginas originais das fontes, especialmente datas de publicação, autoria e títulos, e acrescentar as URLs e datas de acesso conforme o padrão de referências exigido pela instituição de ensino.

## 7. Palavras-chave

Ransomware · Segurança da Informação · Cibersegurança · Malware · Ransomware-as-a-Service · RaaS · Cibercrime · Extorsão Digital · Backup · Resposta a Incidentes · Prevenção · Criptografia
