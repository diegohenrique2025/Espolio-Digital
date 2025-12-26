🔐 Espólio Digital

Sistema de Gestão de Herança Digital e Ativos Post-Mortem.

💻 Sobre o Projeto

O Espólio Digital é uma aplicação web desenvolvida como Projeto Final (Atividade M2) para o curso de Análise e Desenvolvimento de Sistemas da Universidade de Mogi das Cruzes (UMC).

O sistema soluciona o problema crescente da perda de ativos digitais (redes sociais, carteiras de criptomoedas, milhas aéreas, senhas mestras) após o falecimento do titular. Ele atua como um cofre digital seguro onde o usuário cadastra seus bens e designa herdeiros. A liberação dos dados sensíveis (senhas) só ocorre mediante um fluxo de segurança rigoroso, que exige o upload e validação da Certidão de Óbito.

🎯 Principais Funcionalidades

Cofre Digital Criptografado: Cadastro de logins, senhas e frases de recuperação com criptografia AES-256 no banco de dados.

Gestão de Herdeiros: Vínculo de ativos a herdeiros específicos através do CPF.

Agrupamento Inteligente: O herdeiro visualiza os legados agrupados por titular (quem deixou), com status claros ("Em Vida", "Bloqueado", "Liberado").

Solicitação de Desbloqueio: Fluxo onde o herdeiro envia a Certidão de Óbito (PDF) via upload seguro para solicitar acesso aos dados.

Armazenamento Binário: Arquivos de documentos e fotos de perfil são salvos diretamente no banco de dados (LONGBLOB), garantindo maior segurança e integridade.

Interface Responsiva: Telas modernas e adaptáveis a dispositivos móveis, construídas com TailwindCSS.

🛠 Tecnologias Utilizadas

O projeto foi construído utilizando a arquitetura MVC (Model-View-Controller) sem o uso de frameworks pesados de backend, focando na implementação pura do Java EE.

Linguagem: Java (JDK 17)

Backend: Java Servlets, JSP (JavaServer Pages)

Servidor de Aplicação: Apache Tomcat 9.0

Banco de Dados: MySQL 8.0

Frontend: HTML5, CSS3, TailwindCSS (CDN)

Segurança: * SHA-256 para hash de senhas de acesso.

AES-256 para criptografia bidirecional dos ativos digitais.

IDE: Apache NetBeans

🗄️ Estrutura do Banco de Dados

O sistema utiliza 4 tabelas principais relacionais:

usuario: Armazena tanto os titulares quanto os herdeiros. Contém dados pessoais e a foto de perfil em BLOB.

herdeiro: Tabela de vínculo (N:N) que conecta um Titular a um CPF de beneficiário.

ativodigital: Armazena as contas. As colunas senha, frase_recuperacao e mensagem são criptografadas.

solicitacao_liberacao: Registra os pedidos de desbloqueio e armazena o arquivo PDF da certidão em LONGBLOB.

(O script SQL completo para criação do banco encontra-se na pasta /database deste repositório).

🚀 Como Executar o Projeto Localmente

Pré-requisitos

Java JDK 17 ou superior instalado.

Apache NetBeans (v12+) instalado.

MySQL Server rodando.

Apache Tomcat 9.0 configurado no NetBeans.

Passo a Passo

Clone o repositório:

git clone [https://github.com/dibaaloned/Espolio-Digital.git](https://github.com/dibaaloned/Espolio-Digital.git)


Configuração do Banco de Dados:

Abra seu gerenciador MySQL (Workbench/DBeaver).

Crie um banco de dados chamado espoliodigital.

Execute o script database/script_banco.sql para criar as tabelas.

Configuração da Conexão:

Abra o projeto no NetBeans.

Navegue até src/java/config/ConectaDB.java.

Verifique se as credenciais (USER, PASSWORD) correspondem ao seu MySQL local.

Execução:

Clique com o botão direito no projeto > Limpar e Construir.

Clique em Executar (Play). O navegador abrirá na tela de Login.

📸 Telas do Sistema

1. Dashboard do Titular

Painel onde o usuário gerencia seus ativos e herdeiros.

2. Visão do Herdeiro (Legados)

Lista de ativos recebidos com status de bloqueio.

3. Modal de Upload Seguro

Envio da Certidão de Óbito para liberação dos dados.

👥 Autores

Trabalho desenvolvido pelos alunos da UMC (Universidade de Mogi das Cruzes):

Diego Henrique de Oliveira - GitHub

Tiago Kuan Mello Duran Ferreira

Nicoly Fernandes Amancio Martineli

Orientador: Prof. Dr. Adilson Lima da Silva

📄 Licença

Este projeto está sob a licença MIT - veja o arquivo LICENSE para detalhes.
