# Projeto-Cyber-2025---Ransomware-e-Keylogger.
Projeto com intuito de apenas documentar em detalhes estudos, reflexões e aprendizados.

# Desafio de Cybersecurity: Análise e Mitigação de Malware (Perspectiva Blue Team)
# Introdução
Este projeto é uma resposta ao desafio de simulação de malware, com foco na documentação aprofundada e na reflexão estratégica sob a ótica de um Engenheiro de Computação e Pós-graduado em Cybersecurity (Blue Team). Em vez de implementar os códigos de ataque (Ransomware e Keylogger), o foco é em compreender, documentar e propor medidas de defesa e mitigação, transformando o aprendizado em um portfólio técnico de alto valor.

# 1. Ransomware: Análise e Defesa
1.1. O que é Ransomware?
O Ransomware é um tipo de software malicioso que, uma vez executado, criptografa os arquivos da vítima, tornando-os inacessíveis. O atacante então exige um pagamento de resgate (geralmente em criptomoedas) em troca da chave de descriptografia.
1.2. Mecanismo de Ataque (Visão Técnica)
Um ataque de Ransomware tipicamente segue estas etapas:
1.	Vetor de Infecção: Phishing, exploração de vulnerabilidades de software (zero-day ou não corrigidas), ou acesso via RDP (Remote Desktop Protocol) inseguro.
2.	Execução e Persistência: O malware se instala e garante que será executado a cada inicialização do sistema.
3.	Comunicação C2 (Command and Control): O malware se comunica com o servidor do atacante para receber a chave pública de criptografia e enviar informações sobre a vítima.
4.	Criptografia: O malware varre o sistema e a rede em busca de arquivos de valor (documentos, imagens, bancos de dados) e os criptografa usando um algoritmo robusto (ex: AES-256), com a chave de sessão protegida por uma chave pública RSA.
5.	Extorsão: Uma nota de resgate (ransom note) é exibida, informando a vítima sobre a criptografia, o valor do resgate e o prazo para pagamento.

# 1.3. Estratégias de Mitigação (Blue Team)
A defesa contra Ransomware é multicamadas e proativa:
•	Prevenção (Backup 3-2-1): Manter 3 cópias dos dados, em 2 mídias diferentes, com 1 cópia off-site ou offline (imune à rede).
•	Endpoint (EDR - Endpoint Detection and Response): Soluções que monitoram continuamente a atividade do sistema, detectando e bloqueando comportamentos anômalos (ex: criptografia em massa de arquivos).
•	Rede (Segmentação de Rede): Limitar a propagação lateral (lateral movement) do malware, isolando sistemas críticos em VLANs separadas.
•	Usuário (Conscientização e Treinamento): Treinamento contínuo contra ataques de Phishing e engenharia social, o vetor de infecção mais comum.
•	Sistema (Gerenciamento de Patches): Manter sistemas operacionais e softwares (especialmente navegadores e clientes de e-mail) sempre atualizados para corrigir vulnerabilidades conhecidas.
2. Keylogger: Análise e Defesa

# 2.1. O que é Keylogger?
Keylogger (registrador de teclas) é um tipo de software ou hardware que monitora e registra todas as teclas digitadas pelo usuário em um dispositivo. Seu principal objetivo é roubar credenciais, informações financeiras e dados confidenciais.
2.2. Mecanismo de Ataque (Visão Técnica)
Keyloggers podem ser implementados de diversas formas:
1.	Baseado em Software (Hooking): O keylogger se insere (hook) no kernel ou nas APIs do sistema operacional para interceptar os eventos de teclado antes que cheguem ao aplicativo de destino.
2.	Baseado em Hardware: Dispositivos físicos conectados entre o teclado e o computador.
3.	Baseado em Kernel: O mais perigoso, pois opera no nível mais baixo do sistema, sendo extremamente difícil de detectar.
O Keylogger armazena os dados capturados em um arquivo local (.txt ou banco de dados) e, em seguida, os exfiltra (envia) para o atacante, geralmente via e-mail (SMTP) ou requisições HTTP/HTTPS para um servidor C2.


# 2.3. Estratégias de Mitigação (Blue Team)
A defesa contra Keyloggers foca na detecção de comportamento e na proteção de dados em trânsito:
•	Endpoint (HIPS - Host-based Intrusion Prevention System): Monitorar e bloquear tentativas de hooking de APIs e acesso não autorizado a eventos de teclado.
•	Rede (Monitoramento de Tráfego - IDS/IPS): Detectar padrões de exfiltração de dados incomuns (ex: grandes volumes de dados sendo enviados via SMTP ou HTTP para IPs suspeitos).
•	Autenticação (MFA - Multi-Factor Authentication): Mesmo que a senha seja capturada, o segundo fator de autenticação impede o acesso não autorizado.
•	Navegação (Teclados Virtuais): Utilizar teclados virtuais em transações críticas (bancos), pois eles não geram eventos de teclado tradicionais.
•	Análise (Análise Comportamental - UEBA): Soluções que identificam desvios no comportamento normal do usuário (ex: login em horários incomuns ou de locais geográficos distantes).

# 3. Reflexão e Conclusão (Perspectiva Blue Team)
Como profissional de cybersecurity, a maior lição deste desafio é que a segurança é um processo contínuo, não um produto. A simulação de ataques, mesmo que apenas conceitual, reforça a necessidade de:
1.	Visibilidade Total: Não se pode defender o que não se vê. Soluções de EDR e SIEM (Security Information and Event Management) são cruciais para correlacionar eventos e identificar anomalias.
2.	Princípio do Menor Privilégio (PoLP): Limitar as permissões de usuários e aplicações impede que um malware, ao ser executado, cause danos extensos.
3.	Postura Proativa (Threat Hunting): Não esperar que o alarme toque. Buscar ativamente por indicadores de comprometimento (IoCs) e táticas, técnicas e procedimentos (TTPs) de atacantes.
A defesa eficaz contra Ransomware e Keyloggers não reside apenas em antivírus, mas em uma arquitetura de segurança robusta que integra pessoas, processos e tecnologia.

Autor: Marcos Ramos 
Data: 03/11/2025
Tecnologias/Conceitos: Python, Ransomware, Keylogger, Blue Team, EDR, SIEM, MFA, Backup 3-2-1.

