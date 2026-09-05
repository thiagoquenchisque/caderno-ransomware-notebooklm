# Glossário de Conceitos de Ransomware

## 1. Ransomware (Software de Extorsão)

### Definição em linguagem simples

É um tipo de software malicioso (malware) criado especificamente para extorsão financeira. Ele infecta um dispositivo de forma oculta e, em seguida, bloqueia o acesso aos arquivos (geralmente criptografando-os) ou impede o uso do próprio aparelho (bloqueando a tela), exigindo que a vítima pague um resgate para recuperar o acesso.

### Importância para a Segurança da Informação

É a base teórica de todo o ecossistema de ameaças modernas. Compreender que ele se diferencia dos malwares comuns por revelar ativamente sua presença após infectar o sistema é fundamental para definir as prioridades de defesa.

### Exemplo nas fontes

O ataque global do ransomware WannaCry em 2017, que exigiu pagamentos em Bitcoin dos usuários para descriptografar os sistemas afetados.

---

## 2. Ransomware-as-a-Service (RaaS)

### Definição em linguagem simples

É um modelo de negócios criminoso baseado em assinatura ou franquia. Desenvolvedores de malware de elite criam e gerenciam o código e a infraestrutura de pagamentos de ransomware na dark web e os alugam para criminosos parceiros (chamados "afiliados") realizarem os ataques cibernéticos em troca de uma fatia dos resgates coletados.

### Importância para a Segurança da Informação

Explica o crescimento exponencial e a popularização mundial desse crime digital, pois remove a necessidade de o invasor ter habilidades técnicas avançadas de programação de vírus para conduzir um ataque de alta gravidade.

### Exemplo nas fontes

Grupos criminosos como LockBit, Sodinokibi/REvil, Akira, BlackCat e Hive operam ou operavam utilizando o modelo corporativo de RaaS.

---

## 3. Dupla Extorsão (Double Extortion)

### Definição em linguagem simples

É uma tática de ataque em que os cibercriminosos primeiro roubam (exfiltram) cópias de dados corporativos ou pessoais confidenciais e depois executam a criptografia local desses mesmos arquivos. Se a vítima se recusar a pagar para descriptografar os computadores, os atacantes ameaçam publicar ou vender as informações confidenciais roubadas em sites na dark web.

### Importância para a Segurança da Informação

Reduz drasticamente o poder defensivo de ter backups seguros. Mesmo que uma organização consiga restaurar seus sistemas de maneira independente e sem pagar o resgate, ela ainda enfrenta o risco de violação de privacidade de dados, multas de leis regulatórias e sérios danos à reputação corporativa.

### Exemplo nas fontes

O ransomware Maze em 2019 foi o pioneiro a mudar as regras do jogo ao implementar sistematicamente o roubo de dados antes de criptografar e expor amostras das vítimas que se recusavam a pagar.

---

## 4. Tripla Extorsão (Triple Extortion)

### Definição em linguagem simples

É uma evolução agressiva que adiciona novas táticas de intimidação ao modelo de dupla extorsão. Além de criptografar sistemas e ameaçar vazar os dados roubados, os invasores pressionam a vítima executando ataques adicionais de negação de serviço (DDoS) para derrubar sites corporativos ou entrando em contato direto com os clientes, funcionários e fornecedores cujas informações foram roubadas para ameaçá-los e extorqui-los de forma paralela.

### Importância para a Segurança da Informação

Demonstra a profissionalização psicológica do cibercrime. Obriga os times de segurança e de comunicação de crise corporativa a lidarem com impactos externos muito além do perímetro técnico da infraestrutura atacada.

### Exemplo nas fontes

Grupos e gangues de ransomware complementaram suas táticas em 2023 contatando diretamente os clientes das vítimas para coletar pagamentos adicionais e forçar a negociação da organização afetada.

---

## 5. Movimentação Lateral (Lateral Movement)

### Definição em linguagem simples

É a fase em que o invasor, após conseguir infectar um único computador ou endpoint, realiza uma varredura interna na rede corporativa para saltar, expandir e obter o controle de outros computadores, servidores de alto valor e controladores de domínio.

### Importância para a Segurança da Informação

É o momento crítico de contenção antes de um pequeno incidente local se transformar em uma interrupção generalizada de toda a infraestrutura operacional de uma grande empresa.

### Exemplo nas fontes

O grupo Rhysida utiliza e-mails de phishing para obter acesso e beacons do Cobalt Strike para se mover lateralmente nas máquinas afetadas. O malware NetWalker monitorava redes e tentava acessá-las ativamente utilizando os tokens de segurança de todos os usuários conectados no computador infectado.

---

## 6. Backup Offline (Fora da rede / Off-site)

### Definição em linguagem simples

É a criação de cópias de dados importantes que são armazenadas em um dispositivo físico de armazenamento (como discos rígidos externos) ou locais na nuvem que são fisicamente desconectados e isolados do computador ou rede principal de computadores logo após o processo.

### Importância para a Segurança da Informação

É a contramedida primária mais confiável para a recuperação rápida de operações operacionais. Se as unidades de backup forem mantidas conectadas à rede continuamente, os invasores que planejam ataques de ransomware modernos irão localizá-las de forma rotineira para desativá-las, deletá-las ou criptografá-las antes de disparar o ataque no sistema de arquivos ativo.

### Exemplo nas fontes

Recomendações e melhores práticas de segurança indicam a importância do backup offline, demonstrando que unidades conectadas de armazenamento na nuvem podem simplesmente substituir arquivos saudáveis por arquivos criptografados de forma automática em tempo real se houver sincronização direta.

---

## 7. Fileless Ransomware (Ransomware sem arquivo)

### Definição em linguagem simples

É uma técnica em que o ransomware não grava ou executa arquivos executáveis suspeitos no disco rígido do dispositivo. Em vez disso, ele injeta comandos e códigos maliciosos diretamente na memória volátil (RAM) utilizando aplicações legítimas do sistema operacional que já são confiáveis e estão instaladas no computador.

### Importância para a Segurança da Informação

Desafia as defesas tradicionais de antivírus baseadas em assinaturas que varrem apenas o sistema de arquivos local. Exige o uso de ferramentas sofisticadas de comportamento de sistema que analisem scripts e o uso incomum de processos.

### Exemplo nas fontes

Invasores que utilizam a linguagem de script nativa do Windows PowerShell para criptografar dados diretamente na memória RAM sem deixar rastros clássicos em arquivos.

---

## 8. Crypto-Ransomware (Ransomware Criptográfico)

### Definição em linguagem simples

É a variante mais prevalente de ransomware. O malware acessa silenciosamente o sistema, pesquisa por uma lista integrada de extensões de arquivo valiosos (como documentos e planilhas), criptografa os dados desses arquivos usando fortes algoritmos de criptografia e apaga os dados originais, tornando-os ilegíveis até que uma chave seja comprada.

### Importância para a Segurança da Informação

Representa o maior risco de danos duradouros para as operações de TI de uma empresa, pois sem backups saudáveis ou ferramentas específicas, reaver os arquivos sem pagar o resgate pode ser matematicamente impossível.

### Exemplo nas fontes

Famílias como CryptoLocker, Ryuk e Akira operam fundamentalmente como ransomwares criptográficos.

---

## 9. Locker Ransomware (Bloqueador de Tela)

### Definição em linguagem simples

É um tipo de ransomware que impede o acesso físico ou o controle básico da máquina. Ele bloqueia o computador inteiro do usuário substituindo a área de trabalho normal por uma tela cheia contendo uma nota de resgate e, frequentemente, um cronômetro regressivo. Ele bloqueia o teclado e o mouse, impedindo o controle operacional do laptop ou celular, mas mantém as pastas de arquivos e dados intactas por baixo do bloqueio.

### Importância para a Segurança da Informação

Embora cause paralisação operacional, geralmente é muito mais simples e barato de recuperar se comparado ao ransomware criptográfico, já que os arquivos físicos de dados subjacentes não foram alterados ou codificados na unidade local.

### Exemplo nas fontes

Ransomwares focados em sistemas móveis (celulares) preferem usar o tipo locker/bloqueador de tela porque os backups integrados nativos na nuvem desses sistemas portáteis facilitam a neutralização de vírus criptográficos comuns.

---

## 10. Wipers (Limpadores de dados)

### Definição em linguagem simples

É um tipo de malware destrutivo disfarçado de ransomware de sequestro. Ele simula o comportamento básico de criptografia e gera notas de resgate na tela da vítima, mas é projetado internamente para apagar ou destruir permanentemente as tabelas principais de arquivos dos discos rígidos, impossibilitando qualquer descriptografia mesmo que a vítima ceda às demandas de extorsão.

### Importância para a Segurança da Informação

Compreender esse híbrido é vital para que os defensores identifiquem cenários de sabotagem e ataques geopolíticos que se disfarçam de crimes comuns com fins financeiros para causar desordem e pânico em alvos civis ou governamentais.

### Exemplo nas fontes

O malware NotPetya em 2017, que criptografava permanentemente o Registro de Inicialização Principal (MBR) ou a Tabela de Arquivos Mestres (MFT) das máquinas Windows afetadas sem armazenar ou enviar chaves de descriptografia aos invasores, impossibilitando o desbloqueio.

---

## 11. Malspam (Malware Spam)

### Definição em linguagem simples

Abreviação de "malware spam". É o envio massivo ou direcionado de e-mails indesejados (spam) que entregam códigos maliciosos para a caixa de entrada da vítima por meio de links perigosos ou anexos de arquivo infectados.

### Importância para a Segurança da Informação

É amplamente reconhecido como o principal e mais popular canal de infecção utilizado para obter a posição de acesso inicial para o ransomware.

### Exemplo nas fontes

E-mails fraudulentos contendo documentos do Microsoft Word anexados (fingindo ser faturas urgentes) que solicitam que o usuário ative a execução de macros para ler o arquivo, disparando secretamente o download do malware.
