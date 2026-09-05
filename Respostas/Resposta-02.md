# Anatomia de um Ataque de Ransomware

Com base em uma análise rigorosa e exclusiva das fontes do seu notebook, a seguir é detalhada a anatomia completa de um ataque de ransomware, estruturada metodologicamente desde o acesso inicial até a fase final de recuperação pós-incidente.

## Anatomia de um Ataque de Ransomware

### 01. Acesso Inicial

**O que acontece:** O atacante estabelece o primeiro ponto de entrada ou presença dentro da rede ou sistema operacional da organização.

**Objetivo do atacante:** Invadir e obter uma posição inicial sólida no ambiente para poder executar códigos maliciosos.

**Técnicas e mecanismos envolvidos:**

- **E-mails de Phishing e Malspam:** O vetor mais comum. Mensagens falsas que enganam o usuário para clicar em links maliciosos que iniciam downloads silenciosos ou abrir anexos contendo carregamentos executáveis.
- **Exploração de Vulnerabilidades:** Ataques que visam falhas não corrigidas em sistemas operacionais ou aplicativos expostos.
- **Roubo de Credenciais e RDP:** Captura ou compra de logins válidos na dark web, frequentemente para o Protocolo de Área de Trabalho Remota (RDP), para acessar a rede sem disparar alarmes de invasão física.
- **Malvertising e Downloads Drive-by:** Injeção de códigos maliciosos em anúncios legítimos ou sites comprometidos que infectam o usuário sem necessidade de cliques diretos.
- **Mídia Removível (USB):** Dispositivos USB infectados deixados intencionalmente em locais públicos para que funcionários os conectem.

**Características específicas de certas variantes:**

- **GandCrab (PINCHY SPIDER):** Notório por recrutar especialistas em RDP/VNC e spammers profissionais especificamente para redes corporativas.
- **BlackBasta e Ryuk:** Comumente utilizam infecções por outros malwares intermediários, como QakBot, TrickBot ou Emotet, para viabilizar o acesso inicial.
- **Locky:** Utiliza especificamente faturas falsas com macros ocultas em documentos do Microsoft Word.

**Controles de segurança para prevenção e detecção:**

- Implementação de soluções robustas de segurança de e-mail com filtros de conteúdo e varredura de links/anexos.
- Gerenciamento proativo de patches e vulnerabilidades de sistemas operacionais e navegadores.
- Políticas rígidas de acesso, como autenticação multifator (MFA) para RDP e portais externos.
- Programas regulares de treinamento e conscientização de funcionários contra engenharia social e uso de USBs desconhecidos.
- Uso de Web/DNS Filtering para barrar conexões a domínios de reputação duvidosa.

### 02. Execução e Comprometimento do Sistema

**O que acontece:** O código malicioso do ransomware é executado na máquina infectada, iniciando suas funções no sistema sem que o usuário perceba.

**Objetivo do atacante:** Garantir o funcionamento silencioso do malware e assumir o controle dos recursos locais do dispositivo.

**Técnicas e mecanismos envolvidos:**

- **Execução de Binários:** O ransomware executa arquivos binários. 93% dos ransomwares são executáveis baseados em ambiente Windows.
- **Execução de Macros:** O usuário é induzido a habilitar macros no Microsoft Office, o que dispara comandos automáticos de download e execução do ransomware principal.
- **Ferramentas de Acesso Remoto (RAT):** Instalação de uma ferramenta intermediária para manter o controle técnico durante o comprometimento.

**Características específicas de certas variantes:**

- **Fileless Ransomware:** Algumas variantes modernas não deixam rastros no disco rígido. Em vez disso, injetam scripts maliciosos, usando PowerShell, diretamente na memória volátil do sistema para evadir detecções tradicionais de arquivos.

**Controles de segurança para prevenção e detecção:**

- Implementação de soluções de Endpoint Detection and Response (EDR) e ferramentas antivírus de última geração que utilizam inteligência artificial e aprendizado de máquina para analisar comportamentos suspeitos em tempo real.
- Bloqueio estrito de execução de macros em documentos não assinados.
- Uso de Sandboxing para analisar e isolar dinamicamente o comportamento de novos arquivos e aplicações antes de sua execução real na rede.

### 03. Persistência

**O que acontece:** O malware se estabelece de forma oculta e duradoura no sistema comprometido.

**Objetivo do atacante:** Garantir que o acesso ao sistema não seja perdido quando o computador for reiniciado ou o tráfego de rede for interrompido.

**Técnicas e mecanismos envolvidos:**

Embora as fontes do seu notebook não listem de forma exaustiva as chaves de registro técnicas de persistência, elas explicam que o ransomware infecta secretamente e altera credenciais sem que o usuário perceba, utilizando comumente RATs (Remote Access Trojans) que permanecem ativos nos endpoints.

**Controles de segurança para prevenção e detecção:**

- Monitoramento contínuo de endpoints e sistemas para identificar alterações não autorizadas no comportamento aceitável do sistema.
- Auditorias constantes de processos iniciados de forma automática no boot dos sistemas operacionais.

### 04. Elevação de Privilégios

**O que acontece:** O atacante ou o próprio ransomware obtém direitos de acesso mais altos do que o usuário inicial comprometido.

**Objetivo do atacante:** Conseguir permissões de administrador de domínio para alterar configurações críticas de segurança, acessar bancos de dados restritos e desativar proteções locais.

**Técnicas e mecanismos envolvidos:**

- **Comprometimento de Contas:** Captura de senhas ou exploração de brechas que permitam controlar contas com privilégios administrativos.

**Características específicas de certas variantes:**

- **Water Ouroboros (Hunters International):** Utiliza técnicas de extração de credenciais (credential dump) para subir privilégios.
- **DarkSide:** Focado especificamente em roubar credenciais vCenter para atingir ambientes virtualizados corporativos.
- **Petya:** Se não obtiver os privilégios mais altos para criptografar o sistema de arquivos principal (MFT), ele executa um exploit paralelo, como o Mischa, para criptografar arquivos comuns de forma individual.

**Controles de segurança para prevenção e detecção:**

- Implementação do modelo de Segurança Confiança Zero (Zero Trust), onde nenhum usuário ou aplicação é confiável por padrão.
- Adoção de sistemas de Identity Threat Detection and Response (ITDR) e programas robustos de proteção de identidade para monitorar anomalias de comportamento em contas privilegiadas, como Active Directory.
- Controles rígidos de Gerenciamento de Acesso Privilegiado (PAM) e uso de tokens de segurança baseados em nuvem.

### 05. Movimentação Lateral

**O que acontece:** O invasor propaga a infecção ou o acesso remoto a partir do dispositivo inicial para outros computadores, servidores e domínios da mesma rede.

**Objetivo do atacante:** Mapear o ecossistema da rede, atingir sistemas de maior valor e expandir a área de impacto para maximizar o retorno financeiro.

**Técnicas e mecanismos envolvidos:**

- **Varredura de Rede:** Monitoramento e busca ativa por pastas compartilhadas e servidores conectados.
- **Exploits de Rede:** Propagação através de vulnerabilidades conhecidas em protocolos de comunicação que permitem o tráfego lateral de dados.

**Características específicas de certas variantes:**

- **Rhysida e Black Basta:** Utilizam sinalizações (beacons) do Cobalt Strike para fazer a movimentação lateral entre as máquinas.
- **NetWalker:** Varre a rede de maneira autônoma em busca de outros compartilhamentos mapeados e tenta acessá-los utilizando especificamente os tokens de segurança de todos os usuários que estão conectados naquele sistema.
- **WannaCry e NotPetya (Worms Ransomware):** Têm comportamento de autorreplicação (cryptoworms), utilizando o exploit EternalBlue, vulnerabilidade do protocolo SMB do Windows, para saltar de máquina em máquina de forma autônoma sem necessidade de ação humana.
- **Maze:** Conhecido por utilizar os recursos do próprio sistema afetado para saltar lateralmente para as redes de outras empresas parceiras ou clientes.

**Controles de segurança para prevenção e detecção:**

- **Segmentação de rede corporativa:** Divisão da rede em segmentos isolados menores para limitar fisicamente a dispersão de um ransomware e impedir o movimento lateral leste-oeste.
- Uso de soluções de Detecção e Resposta de Rede (NDR) e sistemas de prevenção de intrusões (IPS/IDS) para identificar tráfego de dados e comandos anômalos na rede.

### 06. Coleta e Possível Exfiltração de Dados

**O que acontece:** O ransomware mapeia, reúne e extrai cópias de dados confidenciais e estratégicos da organização e as envia para os servidores dos atacantes antes de iniciar qualquer criptografia.

**Objetivo do atacante:** Obter dados confidenciais para dar ao cibercriminoso um trunfo de extorsão insubstituível, garantindo o pagamento mesmo se a vítima tiver excelentes backups.

**Técnicas e mecanismos envolvidos:**

- **Foco em Dados Estratégicos:** Coleta concentrada de bancos de dados de clientes, informações pessoais (PII), credenciais adicionais, patentes corporativas e registros financeiros.
- **Exportação de Cópias:** Cópia oculta e transferência das informações para fora da infraestrutura da vítima.

**Características específicas de certas variantes:**

- **8Base, Rhysida, Royal, Akira, LockBit e BlackCat:** Adotam o modelo estruturado de Dupla Extorsão, usando sites públicos de vazamento de dados (Data Leak Sites - DLS) para expor amostras dos dados e pressionar a vítima.
- **Water Ouroboros (Hunters International):** Foca prioritariamente no roubo de dados massivos do que na criptografia em si.
- **LockBit e remanescentes da gangue Conti:** Passaram a implantar malwares do tipo infostealer que simplesmente coletam dados e realizam a extorsão sem se dar ao trabalho de bloquear o acesso operacional dos sistemas.

**Controles de segurança para prevenção e detecção:**

- Utilização de softwares de Prevenção de Perda de Dados (DLP) para identificar e impedir a exportação de grandes volumes de informações não autorizadas.
- Criptografia robusta de arquivos confidenciais em repouso.
- Auditorias periódicas e controle rígido de acesso a pastas confidenciais.

### 07. Criptografia ou Destruição de Dados

**O que acontece:** O ransomware executa rotinas de criptografia rápida e destrutiva em arquivos locais e em rede, alterando suas extensões originais e apagando qualquer rastro dos originais.

**Objetivo do atacante:** Inviabilizar o acesso operacional aos dados críticos da vítima de modo a forçá-la a comprar a chave de descriptografia.

**Técnicas e mecanismos envolvidos:**

- **Crypto-Ransomware (Criptográfico):** O malware varre todo o sistema de arquivos localizador por localizador. Ao bater com uma lista de extensões integradas no código, criptografa o arquivo com algoritmos sofisticados e apaga os dados originais. Os arquivos ganham extensões anômalas e recusam-se a abrir.

**Características específicas de certas variantes:**

- **Locker Ransomware:** Não altera ou destrói os dados subjacentes corporativos; em vez disso, bloqueia o console do sistema operacional ou da máquina inteira com uma tela cheia, impedindo o controle de teclado e mouse.
- **Wipers / Ransomware Destrutivo (ex.: NotPetya):** Disfarçam-se de ransomware comum, mas na realidade criptografam ou destroem irreversivelmente a Tabela de Arquivos Mestres (MFT) ou o Registro de Inicialização Principal (MBR), impedindo o Windows de ligar. Não possuem chaves de descriptografia reais para restauração e visam apenas o colapso do alvo.
- **Trigona:** Desenvolveu múltiplas versões permitindo que afiliados digitem argumentos personalizados via linha de comando para realizar criptografia customizada.
- **RansomHub:** Notório por visar especificamente backups mantidos em instâncias de armazenamento em nuvem mal configuradas, como Amazon S3.
- **Ryuk:** Localiza e desativa de forma ativa arquivos de backup e funcionalidades nativas de restauração do sistema antes de iniciar a criptografia geral.

**Controles de segurança para prevenção e detecção:**

- Uso de softwares de segurança em tempo real que bloqueiam operações em massa de gravação de arquivos com base na atividade característica de criptografia em andamento.
- Criação e manutenção de backups desconectados fisicamente (offline e off-site) de dados confidenciais e imagens de sistemas operacionais limpos, evitando que o malware os alcance e os delete.

### 08. Extorsão

**O que acontece:** O malware exibe uma nota de resgate com os canais de negociação e termos do pagamento.

**Objetivo do atacante:** Coagir emocional e financeiramente a vítima para que pague o resgate em criptomoeda não rastreável.

**Técnicas e mecanismos envolvidos:**

- **Notas de Resgate:** Arquivos do tipo `.txt` deixados na área de trabalho ou pop-ups na tela com contagem regressiva.
- **Exigências de Pagamento em Criptomoeda:** Exigência de pagamentos exclusivos em Bitcoin (BTC) ou outros meios anônimos.

**Características específicas de certas variantes:**

- **Double Extortion (Dupla Extorsão):** Ameaça expor dados roubados se o resgate de criptografia não for pago.
- **Triple Extortion (Tripla Extorsão):** Adiciona pressão ao entrar em contato direto com parceiros e clientes cujos dados foram vazados para extorquir pagamentos adicionais deles, ou realiza ataques DDoS simultâneos para tirar serviços de comunicação do ar.
- **8Base:** Utiliza táticas agressivas de "name-and-shame" e expõe dados de organizações sob o pretexto moral de punir empresas que negligenciaram a privacidade de dados.
- **Rhysida:** Passa-se falsamente por uma equipe de auditoria e segurança cibernética tentando "ajudar" a vítima ao apontar falhas em suas redes.
- **Scareware (Falsos Oficiais):** Certas variantes imitam alertas governamentais ou policiais, acusando a vítima de portar arquivos pirateados e exigindo o pagamento de uma "multa".

**Controles de segurança para prevenção e detecção:**

- Não há controle técnico que evite o texto da nota uma vez que o ransomware agiu, mas a proibição ou recusa firme de pagamentos impede que a organização vire um alvo recorrente de extorsão.
- Engajamento imediato de profissionais de resposta a incidentes e conselhos de crise para guiar a comunicação transparente com as partes afetadas.

### 09. Detecção e Resposta ao Incidente

**O que acontece:** A organização identifica a infecção ativa e inicia protocolos de emergência para conter o surto.

**Objetivo do atacante:** Evitar que a organização contenha o malware antes que a criptografia seja concluída, enquanto o objetivo do defensor é interromper a disseminação o mais rápido possível.

**Técnicas e mecanismos envolvidos (Fluxo Operacional de Defesa):**

- **Isolamento Físico de Emergência:** Desconexão imediata de cabos de rede física, desligamento de switches de rede local e desativação de Wi-Fi e conexões Bluetooth.
- **Proteção de Armazenamento:** Desconexão física e imediata de todos os storages de rede e dispositivos de backup conectados antes que sejam criptografados.
- **Identificação:** Coleta de amostras do ransomware e preservação da nota para identificar a família da ameaça e verificar se existem descriptografadores legítimos conhecidos.
- **Remoção de Malware:** Execução de varreduras completas para eliminar resíduos do malware somente após o isolamento estar concluído, de forma a evitar que o malware use o tempo de desinstalação para se espalhar.

**Características específicas de certas variantes:**

- **WannaCry e REvil:** Algumas variantes podem ser contidas desligando-se o sistema e reiniciando a máquina em Modo Seguro para instalar softwares de defesa, embora variantes modernas consigam persistir até mesmo nessa condição.

**Controles de segurança para prevenção e detecção:**

- Uso de plataformas de Orquestração, Automação e Resposta de Segurança (SOAR) ou agentes integrados para isolar e matar processos maliciosos automaticamente em milissegundos.
- Desenvolvimento e treinamento exaustivo de um Plano de Resposta a Incidentes de TI estruturado.
- Notificação rápida das autoridades policiais responsáveis, como o IC3.

### 10. Recuperação

**O que acontece:** A organização limpa os ambientes comprometidos e inicia o restabelecimento seguro da infraestrutura e dos dados.

**Objetivo do atacante:** Desencorajar a recuperação livre exigindo resgate, mas o objetivo da organização é reconstruir as operações de forma independente e limpa.

**Técnicas e mecanismos envolvidos:**

- **Restauração Segura de Backups:** Importação das cópias de segurança offline e verificação de versões históricas em nuvem que tenham sobrevivido à infecção. A recuperação de dados só deve ser iniciada após a remoção total do vírus, ou os dados novos serão criptografados novamente.
- **Reconstrução de Sistemas (Bare-Metal):** Formatação completa do armazenamento de todas as máquinas afetadas e reinstalação limpa dos sistemas operacionais e softwares confiáveis.
- **Descriptografadores Legítimos:** Uso de ferramentas e chaves de descriptografia gratuitas disponibilizadas por canais oficiais de segurança cibernética, como o projeto No More Ransom. Deve-se evitar descriptografadores encontrados em mecanismos de busca comuns, pois costumam ser disfarces de novos malwares.

**Características específicas de certas variantes:**

- **SentinelOne Singularity:** Se a máquina tiver este tipo de agente instalado no momento do ataque, a organização pode utilizar a capacidade nativa de Rollback para reverter em poucos cliques as modificações e arquivos criptografados para o estado exato de antes da invasão.

**Controles de segurança para prevenção e detecção:**

- Implementação da Regra de Backup 3-2-1 (3 cópias de dados, em 2 mídias diferentes, sendo 1 offline/off-site).
- Adoção de arquiteturas de armazenamento na nuvem com versionamento histórico imutável que permitam retornar facilmente a versões não criptografadas dos arquivos.
- Testes periódicos de restauração de backups para garantir a continuidade operacional.

## Resumo Comparativo: Comum vs. Variantes Específicas

| Característica de Ataque | Status de Adoção nas Ameaças | Exemplos Técnicos |
|---|---|---|
| **Phishing e Malspam** | Comum (Vetor principal de entrada na internet) | Utilizado pela imensa maioria das famílias de malware e ransomware. |
| **Criptografia Simétrica de Arquivos** | Comum (O comportamento base do malware de sequestro) | CryptoLocker, Ryuk, LockBit e Akira. |
| **Dupla Extorsão (Roubo + Criptografia)** | Comum (Adoção em massa após 2019) | Rhysida, Royal, Akira, LockBit, BlackCat e Maze. |
| **Modelo de Ransomware-as-a-Service (RaaS)** | Comum (Negócio criminoso moderno com afiliados) | RansomHub, Akira, LockBit, BlackCat, Dharma, REvil e Conti. |
| **Fileless Ransomware (Execução em Memória)** | Especificidade de Variante (Evita detecção tradicional de arquivo) | Utiliza scripts em linguagens como PowerShell para rodar diretamente na RAM. |
| **Criptoworms (Auto-propagação em rede)** | Especificidade de Variante (Explora falhas de protocolo lateral) | WannaCry e NotPetya usando o exploit EternalBlue. |
| **Ataque à Tabela Master de Arquivos (MBR/MFT)** | Especificidade de Variante (Destrutivo e impede o boot do SO) | Petya e NotPetya. |
| **Exfiltração sem Criptografia (Infostealer puro)** | Especificidade de Variante (Tática moderna baseada em roubo de dados) | LockBit e ex-associados do Conti utilizam em casos de alta preparação de defesa. |
