# Resumo Estruturado sobre Ransomware

## 1. Conceito de Ransomware

O ransomware é uma classe específica de malware (software malicioso) projetada com o objetivo explícito de extorsão financeira. O programa funciona infectando secretamente um dispositivo, bloqueando o acesso aos dados da vítima — geralmente por meio de criptografia forte — ou impedindo o uso do próprio sistema operacional.

Uma vez que os dados ou o sistema são feitos de "reféns digitais", o atacante apresenta uma nota de resgate exigindo um pagamento (atualmente em criptomoedas como o Bitcoin) em troca da chave de descriptografia para reaver os dados.

> **Destaque Acadêmico:** O ransomware representa a convergência entre a evolução do software malicioso e a descentralização financeira. A introdução de criptomoedas não rastreáveis (como o Bitcoin em 2009) é o marco histórico que viabilizou a explosão dessa atividade criminosa em escala global, eliminando intermediários financeiros no processo de extorsão.

## 2. Diferença entre Ransomware e Malware

A relação conceitual entre esses termos é estritamente hierárquica:

- **Malware:** É o termo genérico e guarda-chuva para qualquer software malicioso desenvolvido para causar danos, roubar dados ou violar sistemas. Engloba vírus, cavalos de Troia (trojans), spyware, botnets, infostealers e criptomineradores.
- **Ransomware:** É uma subcategoria ou tipo específico de malware.

**Diferença Funcional Importante:** Enquanto a maioria das ameaças de malware (como o spyware) lucra ao permanecer oculta e silenciosa no sistema pelo maior tempo possível, o ransomware adota uma estratégia oposta: ele só gera lucro para o cibercriminoso no momento em que revela sua presença de forma barulhenta e explícita, comunicando à vítima que seus arquivos foram bloqueados e detalhando as instruções para o pagamento.

> **Destaque Acadêmico:** Para fins acadêmicos, deve-se rejeitar a confusão comum de que "ransomware" e "vírus" são sinônimos. Os vírus são classificados pela sua capacidade de autorreplicação e infecção de outros programas, enquanto o ransomware é classificado pelo seu comportamento de bloqueio e extorsão. Todo ransomware é malware, mas nem todo malware é ransomware.

## 3. Principais Tipos de Ransomware

As fontes dividem os ransomwares em categorias com base em como o malware manipula os dados e os dispositivos afetados:

- **Crypto-Ransomware (ou Criptográfico):** O tipo mais comum. Ele criptografa arquivos individuais de valor (documentos, fotos, bancos de dados) no dispositivo e na rede, mas mantém o sistema operacional em execução apenas o suficiente para que a vítima veja as exigências.
- **Locker Ransomware (ou Bloqueador de Tela):** Menos comum. Em vez de criptografar dados, ele bloqueia o usuário inteiramente fora de seu sistema operacional. Uma tela cheia com um aviso de resgate (e frequentemente um temporizador regressivo) é exibida, impedindo o controle de teclado e mouse. Os arquivos permanecem intactos por baixo.
- **Leakware / Doxware (Focado em Roubo de Dados):** Projetado para roubar (exfiltrar) dados corporativos e pessoais confidenciais antes (ou em vez) de criptografá-los. A extorsão reside na ameaça de vazar ou vender essas informações confidenciais em sites de vazamento na dark web (Data Leak Sites - DLS).
- **Scareware:** Utiliza táticas psicológicas de medo e urgência. Costuma exibir alertas falsos fingindo ser de autoridades policiais (acusando o usuário de pirataria ou pornografia) ou softwares antivírus falsos, coagindo a vítima a pagar uma "multa" ou comprar um programa inútil para limpar um sistema que não possui vírus reais.
- **Wipers (Ransomware Destrutivo):** Variantes cujo único objetivo é destruir ou inutilizar permanentemente os dados, sem qualquer intenção real de fornecer chaves de descriptografia, mesmo que o resgate seja pago.

> **Destaque Acadêmico e Contradições:** Existe uma divergência conceitual relevante entre as instituições de segurança sobre os Wipers:
>
> A Check Point Software afirma que wipers como o NotPetya não são ransomwares verdadeiros, pois mascaram seu comportamento destrutivo de apagamento de dados sob a identidade visual de um ransomware comum para enganar as vítimas, impossibilitando qualquer descriptografia.
>
> A CrowdStrike, por sua vez, lista o NotPetya de forma legítima em sua taxonomia e histórico como uma variante de ransomware autorreplicante de alta periculosidade.

## 4. Anatomia e Etapas de um Ataque

Para descrever as fases do ataque, as fontes trazem duas visões principais. A mais detalhada e estruturada academicamente é o Modelo de 5 Estágios da IBM Security:

**[Estágio 1: Acesso Inicial] ➔ [Estágio 2: Pós-Exploração] ➔ [Estágio 3: Entender e Expandir] ➔ [Estágio 4: Coleta e Exfiltração] ➔ [Estágio 5: Implementação e Envio da Nota]**

### Estágio 1: Acesso Inicial

O invasor ganha presença na rede corporativa ou no endpoint através de falhas, credenciais roubadas ou engenharia social.

### Estágio 2: Pós-Exploração

O atacante implanta ferramentas intermediárias, como Trojans de Acesso Remoto (RATs) ou outros malwares para solidificar sua posição e manter a presença.

### Estágio 3: Entender e Expandir (Reconhecimento e Movimentação Lateral)

Os invasores mapeiam ativamente a infraestrutura de TI, identificando computadores, servidores de alto valor e controladores de domínio. Eles utilizam a movimentação lateral para saltar de máquina em máquina e expandir o controle.

### Estágio 4: Coleta e Exfiltração de Dados

Foco em localizar, extrair e enviar cópias dos dados confidenciais mais valiosos (propriedade intelectual, dados financeiros e credenciais de login) para os servidores do atacante.

### Estágio 5: Implementação e Envio da Nota

Ativação do ransomware. O código criptografa os arquivos, frequentemente localiza e destrói ou criptografa backups conectados, e exibe a nota de resgate (`.txt` ou pop-up) com instruções de pagamento.

> **Destaque Acadêmico:** O ataque de ransomware moderno não é um evento instantâneo. O processo de exfiltração de dados e reconhecimento de rede pode durar dias ou semanas de forma silenciosa antes que a criptografia — que é a última etapa visível e dura minutos ou horas — seja disparada. A velocidade de implementação média após o ganho de acesso à rede é de menos de quatro dias.

## 5. Principais Formas de Acesso Inicial

Os cibercriminosos exploram uma série de vetores para estabelecer a presença inicial em um sistema ou rede:

- **E-mails de Phishing e Malspam (Malware Spam):** O vetor disparado mais comum. O usuário é induzido a clicar em um link malicioso ou abrir anexos (como PDFs ou Word) com macros ocultas. Habilitar essas macros executa comandos ocultos que baixam silenciosamente o payload do ransomware.
- **Vulnerabilidades em Softwares e Sistemas Operacionais (Unpatched):** Exploração de brechas de segurança conhecidas ou vulnerabilidades de dia zero (zero-day). Um exemplo histórico é o WannaCry em 2017, que explorou de forma automatizada o exploit EternalBlue no protocolo SMB do Windows.
- **Roubo de Credenciais e RDP (Remote Desktop Protocol):** Logins válidos são roubados, comprados na dark web ou adivinhados via ataques de força bruta. O RDP da Microsoft é um dos alvos preferenciais para invasores de ransomware entrarem de forma legítima nas redes corporativas.
- **Downloads Drive-by e Malvertising:** Sites infectados que baixam automaticamente o ransomware ao serem visitados (drive-by), ou injeção de scripts maliciosos dentro de redes de anúncios de publicidade legítima (malvertising).
- **Dispositivos USB Desconhecidos:** Pendrives infectados abandonados intencionalmente em locais públicos por atacantes. O malware é ativado quando um usuário curioso o conecta ao seu dispositivo.

> **Destaque Acadêmico:** Para as PMEs, um vetor de acesso negligenciado é o fator BYOD (Bring Your Own Device). A CrowdStrike documenta que empresas menores frequentemente dependem de computadores de uso pessoal misto de seus funcionários, abrindo portas para que atividades pessoais desprotegidas (como navegação em redes inseguras) tragam ameaças para o ambiente de trabalho.

## 6. Criptografia, Exfiltração e Extorsão

Esses conceitos representam o tripé que sustenta a lucratividade e o poder de barganha das gangues de cibercriminosos:

### Criptografia

O software varre o sistema local e pastas compartilhadas de rede mapeadas. Ele substitui os arquivos originais por versões codificadas com fortes algoritmos criptográficos e apaga todos os registros dos arquivos originais. O invasor detém a única senha capaz de descriptografá-los.

### Exfiltração

Antes de ativar o bloqueio, os atacantes transferem cópias dos bancos de dados estratégicos corporativos para sua própria infraestrutura.

### Evolução dos Modelos de Extorsão

- **Extorsão Simples:** Criptografia local de dados com cobrança de resgate pela chave de descriptografia.
- **Dupla Extorsão (Double Extortion):** Os atacantes exigem resgate para descriptografar os sistemas locais e adicionam a ameaça de vazar publicamente ou vender os dados exfiltrados (caso a vítima tenha backups funcionais e recuse-se a pagar pelo desbloqueio).
- **Tripla Extorsão (Triple Extortion):** Além da criptografia e do vazamento, os atacantes elevam a pressão executando ataques adicionais de negação de serviço (DDoS) para derrubar os canais de comunicação da vítima ou entrando em contato direto com os clientes, funcionários e parceiros da vítima cujos dados foram vazados para extorquir pagamentos diretos deles.
- **Ransomware-as-a-Service (RaaS):** O modelo operacional corporativo do crime digital. Desenvolvedores criam o malware e gerenciam as estruturas de pagamento na dark web, alugando o kit de ataque para criminosos menos técnicos (afiliados) realizarem os ataques e dividirem a receita dos resgates.

## 7. Exemplos e Variantes de Ransomware

As fontes trazem um catálogo extenso de variantes notáveis pelo seu pioneirismo ou impacto histórico:

- **AIDS Trojan (1989):** O primeiro ransomware documentado, criado pelo biólogo Joseph L. Popp e distribuído via disquetes na conferência da OMS. Ele apenas ocultava e criptografava os nomes dos arquivos, exigindo US$ 189 enviados a uma caixa postal no Panamá.
- **CryptoLocker (2013):** Considerado o iniciador da era moderna do ransomware. Utilizou a botnet Gameover Zeus para causar mais de um milhão de infecções com criptografia forte e pioneira.
- **WannaCry (2017):** O primeiro criptoworm autorreplicante de grande escala. Espalhou-se sozinho por redes vulneráveis ao EternalBlue, paralisando serviços cruciais como o NHS do Reino Unido.
- **NotPetya (2017):** Variante altamente destrutiva que bloqueava o Master Boot Record (MBR) de computadores Windows. Revelou-se um wiper de dados, pois a recuperação de arquivos era impossível, visando apenas o colapso operacional do alvo.
- **Ryuk:** Popularizou a tática de "Big Game Hunting" (caça a grandes alvos) contra alvos corporativos e governamentais de alto valor, cobrando resgates milionários.
- **Maze (2019):** Criador e popularizador da técnica de dupla extorsão ao implementar o roubo sistemático de dados antes do bloqueio local.
- **LockBit:** Uma das cepas de maior prevalência em 2023, notória pela sua postura profissionalizada de gerenciamento e aquisição de outras cepas de malware para compor seu arsenal.
- **Conti:** Cartel cibercriminoso de RaaS desmantelado em 2022 que pagava salários regulares para afiliados e cujos remanescentes criaram ameaças atuais como o Black Basta e Royal.
- **Water Ouroboros (Hunters International):** Sucessor em código do Hive ransomware, focado muito mais no roubo massivo de dados do que propriamente na criptografia.

## 8. Impactos para Organizações

Os efeitos de um surto de ransomware são sistêmicos e dividem-se em várias frentes:

### Downtime e Interrupção Operacional

Paralisia imediata de sistemas operacionais, cancelamento de serviços (como consultas médicas canceladas no NHS durante o WannaCry), interrupção de vendas e ociosidade de equipes.

### Custos de Resgate vs. Custos de Violação

O custo total médio de uma violação por ransomware alcançou US$ 5,68 milhões corporativos (dados da IBM, sem incluir o custo do resgate pago), enquanto a Trend Micro aponta uma média histórica de US$ 4,4 milhões por incidente. As notas de resgate individuais rotineiramente ultrapassam os 6 ou 7 dígitos.

### Danos de Reputação e Regulatórios

O vazamento de informações confidenciais (PII) acarreta litígios judiciais, danos duradouros à imagem de mercado da marca e aplicação de multas pesadas por órgãos de proteção de dados.

### Dilema Ético e Legal do Pagamento

As autoridades de segurança pública (como o FBI e a NCIJTF) desaconselham de forma unânime o pagamento do resgate, argumentando que isso financia atividades criminosas, incentiva futuros ataques e não garante a devolução ou integridade dos dados.

De acordo com dados de mercado, menos de 50% dos que pagam o resgate conseguem de fato recuperar seus sistemas com sucesso devido a falhas em descriptografadores fornecidos ou incompatibilidades operacionais.

Em determinadas jurisdições, o pagamento de resgate é considerado ilegal se os atacantes estiverem sob sanções econômicas americanas (como Irã e Coreia do Norte), ou se a vítima for um órgão estatal (como na Flórida e Carolina do Norte).

> **Destaque Acadêmico e Contradições:** O artigo de Kurt Baker (CrowdStrike), com base em dados globais de 2021, aponta que 96% das vítimas que cederam ao primeiro pagamento de resgate foram extorquidas novamente por taxas adicionais. Já o relatório de Matthew Kosinski (IBM), com dados da Coveware de 2023, aponta uma tendência encorajadora: apenas 37% das empresas vítimas optaram por pagar resgates em 2023 (uma queda comparada a 70% em 2020), indicando que os investimentos organizacionais em backups e defesas ativas estão enfraquecendo o poder financeiro das gangues.

## 9. Prevenção e Controles de Segurança

Para reduzir a superfície de exposição ao ransomware, recomenda-se uma estratégia de segurança em múltiplas camadas (defesa em profundidade):

- **Backups Robustos (Regra 3-2-1):** Manter pelo menos 3 cópias de segurança em 2 tipos diferentes de armazenamento, com pelo menos 1 cópia mantida offline ou desvinculada fisicamente da rede corporativa. Backups que permanecem constantemente conectados no momento da ativação do ransomware são mapeados e criptografados de forma rotineira pelo malware.
- **Gerenciamento Proativo de Patches:** Manutenção rigorosa de atualizações de sistemas operacionais, aplicativos e navegadores para fechar portas de exploração de vulnerabilidades.
- **Endpoint Detection and Response (EDR) e Antivírus de Última Geração (NGAV):** Softwares de segurança que utilizam inteligência artificial e aprendizado de máquina para analisar em tempo real o comportamento de processos e bloquear tentativas em massa de criptografia ou desativação de ferramentas de defesa.
- **Segurança de E-mail Avançada:** Implementação de varreduras ativas de links, filtros de spam, análise de anexos por sandboxing e restrição de e-mails contendo arquivos executáveis suspeitos ou macros.
- **Segmentação de Rede:** Divisão de redes corporativas em segmentos lógicos menores para deter o movimento lateral de ransomwares worms, impedindo a disseminação horizontal (leste-oeste).
- **Gestão de Identidade e Modelo Zero Trust (Confiança Zero):** Reduzir privilégios locais e de redes corporativas. Utilização de autenticação multifator (MFA), gerenciamento de contas privilegiadas (PAM) e soluções de detecção de ameaças de identidade (ITDR).
- **Filtros de URL (Web Filtering):** Criação de barreiras ativas contra navegação de usuários em domínios maliciosos ou URLs inseguras não verificadas.

## 10. Detecção, Resposta e Recuperação

Caso ocorra uma infecção ativa, as fontes detalham as etapas operacionais necessárias para mitigar o dano:

### Detecção de Sintomas Técnicos

Sinais como modificações anômalas rápidas de arquivos, renomeação de extensões originais, lentidão severa inexplicável no processamento de disco, desativação de antivírus locais sem ação do usuário e surgimento de arquivos de texto de notas de resgate.

O uso de honeypots (pastas de arquivos falsos atuando como iscas) também ajuda na detecção precoce.

### Roteiro de Resposta a Incidentes (Contenção Operacional)

- **Isolamento Físico de Emergência:** Desconectar imediatamente os cabos de rede física do dispositivo infectado, desativar conexões Wi-Fi locais, conexões Bluetooth e desligar o sistema para impedir a propagação horizontal.
- **Proteção dos Storages:** Desconectar fisicamente todos os dispositivos de armazenamento anexados à rede e discos rígidos externos conectados.
- **Identificação da Variante:** Preservar a nota de resgate e amostras dos arquivos criptografados para auxiliar os especialistas a determinarem qual família técnica de ransomware causou o ataque.
- **Remoção Segura do Malware:** Realizar varreduras antivírus completas e remoção do código malicioso apenas após o isolamento e identificação. Iniciar a desinstalação sem isolamento prévio pode fazer o ransomware usar o tempo de execução para acelerar sua proliferação interna.
- **Preservação de Evidências e Comunicação:** Fotografar a nota de resgate, salvar amostras de e-mails suspeitos que causaram o ataque e registrar Boletim de Ocorrência policial em canais de cibercrime corporativo, como o IC3 nos EUA.

### Recuperação de Dados

- **Restauração Segura de Backups:** Utilização das cópias isoladas ou do versionamento histórico limpo na nuvem. **Alerta:** a restauração só pode ser iniciada após a remoção total do vírus do sistema, caso contrário, os dados restaurados serão criptografados novamente.
- **Reconstrução Bare-Metal:** Formatação e reinstalação limpa de fábrica de sistemas operacionais de todos os computadores comprometidos da organização.
- **Ferramentas Oficiais Gratuitas:** Consulta a projetos mundiais de cooperação contra o cibercrime como o No More Ransom, que disponibiliza chaves legítimas e descriptografadores apreendidos pela polícia.
- **Sistemas de Rollback Integrados:** Utilização de ferramentas avançadas de endpoints, como o SentinelOne Singularity, que usam armazenamento temporário local e rollback automatizado baseado em comportamento para reverter as alterações de arquivos criptografados de volta ao estado exato anterior com poucos cliques.
