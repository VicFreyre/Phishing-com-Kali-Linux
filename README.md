# Phishing-com-Kali-Linux
Este repositório contém um relatório técnico sobre a simulação de um ataque de phishing usando Kali Linux e o Social Engineering Toolkit (SET). O objetivo é demonstrar métodos de captura de credenciais em um ambiente controlado, promovendo a conscientização sobre segurança cibernética e fornecendo recomendações para prevenção de phishing.

## 1. Introdução
Este relatório documenta a execução de um experimento de segurança ofensiva utilizando o Kali Linux para simular um ataque de phishing. O objetivo é compreender os métodos utilizados por agentes maliciosos e reforçar o conhecimento sobre segurança cibernética, sempre dentro de um ambiente controlado e ético.

## 2. Ambiente de Testes
- **Sistema Operacional:** Kali Linux  
- **Ferramenta Utilizada:** Social Engineering Toolkit (SET)  
- **Método de Ataque:** Credential Harvester Attack + Site Cloner  
- **Alvo Simulado:** Página de login do Facebook 

## 3. Configuração do Phishing no Kali Linux

### 3.1 Acessando o SEToolkit
Execute o comando abaixo para iniciar o SEToolkit:
bash
sudo setoolkit

Quando solicitado, selecione as seguintes opções:
1. **Social-Engineering Attacks**
2. **Website Attack Vectors**
3. **Credential Harvester Attack Method**
4. **Site Cloner**

### 3.2 Obtendo o Endereço da Máquina
Para que as vítimas acessem a página clonada, é necessário identificar o endereço IP do Kali Linux. Use:
bash
ifconfig

Ou no caso de versões mais recentes do Linux:
bash
ip a

Anote o endereço IP (exemplo: 192.168.0.105).

### 3.3 Clonando o Site Alvo
No SEToolkit, forneça o endereço da máquina (IP) e o site a ser clonado:
bash
Enter the IP address for the POST back in Harvester/Tabnabbing: 192.168.0.105
Enter the URL to clone: http://www.facebook.com

O SET gerará uma cópia da página de login e começará a capturar credenciais.

### 3.4 Captura de Credenciais
Quando um usuário inserir dados na página falsa, as credenciais serão armazenadas no seguinte arquivo:
bash
/var/www/html/harvester.log

Para visualizar:
bash
cat /var/www/html/harvester.log


## 4. Resultados
A execução do experimento demonstrou que um atacante pode enganar usuários desatentos para capturar credenciais. Abaixo está um exemplo fictício de credenciais capturadas:
POSSIBLE USERNAME FIELD FOUND: email=joao@gmail.com
POSSIBLE PASSWORD FIELD FOUND: pass=passwd


## 5. Medidas de Mitigação
Para prevenir ataques de phishing, recomenda-se:
1. **Ativar a autenticação em dois fatores (2FA).**
2. **Evitar clicar em links desconhecidos ou suspeitos.**
3. **Utilizar gerenciadores de senhas para evitar reutilização de credenciais.**
4. **Verificar se a URL do site está correta antes de inserir informações sensíveis.**
5. **Manter sistemas e navegadores atualizados para bloquear sites fraudulentos.**

## 6. Conclusão
Este experimento ilustra como um ataque de phishing pode ser realizado por agentes mal-intencionados. O conhecimento desses métodos permite que profissionais de segurança desenvolvam melhores estratégias de defesa. Sempre que realizar testes de segurança, certifique-se de que está em um ambiente controlado e autorizado.

**Nota:** Este estudo foi realizado com fins educacionais e não deve ser utilizado para atividades maliciosas.

