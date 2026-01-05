MonkChat
MonkChat Logo
Uma aplicação de chat em tempo real moderna e intuitiva
📋 Visão Geral
MonkChat é uma aplicação completa de chat em tempo real que permite aos usuários criar salas, enviar mensagens públicas ou privadas, editar mensagens enviadas, e gerenciar suas contas de usuário. Este repositório contém o código da aplicação, dividido em frontend (React) e backend (Node.js/Express).

🚀 Tecnologias Utilizadas
Frontend
React 19.1.0: Biblioteca JavaScript para construção da interface com o mais recente sistema de renderização e hooks
React Router 7.6.0: Gerenciamento avançado de navegação e rotas com recursos de memorização e lazy loading
CSS Modular: Estilização com CSS puro organizado em módulos por componente
React Toastify 11.0.5: Sistema completo de notificações toast personalizadas
React Top Loading Bar 3.0.2: Indicadores de carregamento superiores para melhor UX
Axios 1.9.0: Cliente HTTP robusto para comunicação com o backend
Styled Components 6.1.18: Biblioteca para estilização de componentes (parcialmente migrada para CSS puro)
Backend
Node.js: Ambiente de execução JavaScript
Express: Framework para criação de APIs RESTful
MySQL: Banco de dados relacional
dotenv: Gestão de variáveis de ambiente
cors: Configuração de políticas de compartilhamento entre origens
nodemon: Desenvolvimento com recarga automática do servidor
🔍 Principais Funcionalidades
Autenticação e Gerenciamento de Usuários
Sistema completo de login: Autenticação com email/senha e armazenamento seguro em localStorage
Cadastro intuitivo: Registro de novos usuários com validações em tempo real
Perfil de usuário: Alteração de nickname e redefinição de senha com confirmação
Sessões de usuário: Gerenciamento de sessões com logout seguro
Validação de credenciais: Verificação segura de senhas e emails
Chat Avançado
Criação e gestão de salas: Interface para criar salas de chat com nomes personalizados
Sistema de participantes: Visualização de usuários online em cada sala
Mensagens públicas e privadas: Envio de mensagens para todos ou para usuários específicos
Edição inline de mensagens: Possibilidade de editar mensagens enviadas com indicador visual
Notificações de entrada: Avisos automáticos quando usuários entram nas salas
Histórico completo: Carregamento e visualização do histórico de conversas
Atualização automática: Polling otimizado para atualização de novas mensagens (a cada 5 segundos)
Interface Responsiva
Design adaptativo: Layout responsivo para dispositivos desktop, tablet e mobile
Sistema de notificações: Toasts para feedback de ações bem-sucedidas e erros
Indicadores de carregamento: Barras de progresso para operações assíncronas
Animações e transições: Feedback visual para interações do usuário
Modo de edição contextual: Interface intuitiva para edição de mensagens
📁 Estrutura do Projeto
Frontend
monkchat/frontend/
├── public/                      # Arquivos públicos
│   ├── assets/
│   │   └── images/              # Imagens e ícones
│   ├── index.html               # HTML principal
│   ├── manifest.json            # Manifesto da aplicação web
│   └── robots.txt               # Configurações para crawlers
├── src/
│   ├── components/              # Componentes reutilizáveis
│   │   ├── cabecalho/           # Componente de navegação superior
│   │   └── outros/              # Componentes UI compartilhados
│   ├── pages/                   # Páginas da aplicação
│   │   ├── alterar/             # Alteração de perfil e senha
│   │   ├── cadastro/            # Registro de usuários
│   │   ├── login/               # Autenticação de usuários
│   │   └── monkchat/            # Interface principal do chat
│   ├── service/
│   │   └── api.js               # Integração com backend via Axios
│   ├── index.css                # Estilos globais
│   ├── index.js                 # Ponto de entrada da aplicação
│   └── routes.js                # Configuração de rotas
└── package.json                 # Dependências e scripts
Backend
monkchat/backend/
├── .env                     # Variáveis de ambiente
├── .gitignore               # Configurações de exclusão para Git
├── package.json             # Dependências e scripts do projeto
├── README.md                # Documentação do projeto
└── src/
        ├── app.js               # Configuração do Express
        ├── db.js                # Conexão com o banco de dados MySQL
        ├── server.js            # Inicialização do servidor
        ├── controllers/         # Controladores de lógica de negócios
        │   ├── MessageController.js    # Gerenciamento de mensagens
        │   ├── ParticipantController.js # Gerenciamento de participantes
        │   ├── RoomController.js       # Gerenciamento de salas
        │   └── UserController.js       # Gerenciamento de usuários
        ├── repositories/        # Acesso ao banco de dados
        │   ├── MessageRepository.js
        │   ├── ParticipantRepository.js
        │   ├── RoomRepository.js
        │   └── UserRepository.js
        └── routes/              # Definição de rotas da API
                ├── index.js         # Agrupamento de rotas
                ├── messageRoutes.js # Rotas para mensagens
                ├── roomRoutes.js    # Rotas para salas
                └── userRoutes.js    # Rotas para usuários
💻 Detalhes de Implementação
Frontend
Sistema de Autenticação
Armazenamento seguro: Dados de usuário persistidos em localStorage com controle de sessão
Proteção de rotas: Redirecionamento automático para tela de login quando não autenticado
Validações robustas: Verificação de campos obrigatórios e formatos de entrada
Feedback de erros: Mensagens específicas para problemas de autenticação
Gerenciamento de Estado
Hooks modernos: Uso extensivo de useState, useEffect, useRef e useCallback
Estados locais eficientes: Gerenciamento otimizado de componentes
Referências persistentes: Uso de useRef para elementos DOM e intervalos
Efeitos controlados: Limpeza adequada de efeitos para evitar memory leaks
Interface do Chat
Layout flexível: Visualização adaptada para diferentes dispositivos
Sistema de rolagem inteligente: Rolagem automática para novas mensagens com detecção de posição
Edição contextual: Interface inline para edição de mensagens próprias
Indicadores visuais: Feedback claro para mensagens próprias e de outros usuários
Filtro de mensagens: Visualização seletiva de mensagens públicas e privadas
Formatação de data/hora: Exibição amigável de carimbos de tempo
Otimizações de Performance
Memoização de funções: Uso de useCallback para evitar rerenderizações desnecessárias
Debouncing de eventos: Controle de frequência de atualizações do chat
Renderização condicional: Componentes carregados apenas quando necessário
Carregamento eficiente: Limitação de mensagens carregadas por requisição
Backend
Arquitetura
Padrão MVC: Separação clara entre modelos, visualizações e controladores
Repositories: Camada de abstração para acesso ao banco de dados
Middleware: Funções para processamento de requisições
Error Handling: Tratamento centralizado de erros
Banco de Dados
MySQL: Armazenamento relacional de usuários, salas, participantes e mensagens
Connection Pool: Gerenciamento eficiente de conexões
Queries Otimizadas: Buscas SQL otimizadas para melhor performance
🔧 Instalação e Configuração
Pré-requisitos
Node.js 14.x ou superior
MySQL 5.7 ou superior
NPM 6.x ou superior ou Yarn 1.22.x ou superior
Conexão com internet (para instalar as dependências)
Backend
Clone o repositório:

git clone https://github.com/seu-usuario/monkchat.git
cd monkchat/backend
Instale as dependências:

npm install
Configure as variáveis de ambiente criando um arquivo .env na raiz do diretório backend:

DB_HOST=localhost
DB_USER=seu_usuario
DB_PASSWORD=sua_senha
DB_DATABASE=chat_db
DB_CONNECTION_LIMIT=10
PORT=3001
Crie o banco de dados e as tabelas necessárias:

CREATE DATABASE chat_db;
USE chat_db;

-- Tabela de usuários
CREATE TABLE TB_USUARIO (
    ID_USUARIO INT PRIMARY KEY AUTO_INCREMENT,
    NM_USUARIO VARCHAR(100) NOT NULL,
    DS_EMAIL VARCHAR(200) UNIQUE NOT NULL,
    DS_SENHA VARCHAR(100) NOT NULL
);

-- Tabela de salas
CREATE TABLE TB_SALA (
    ID_SALA INT PRIMARY KEY AUTO_INCREMENT,
    ID_USUARIO INT,
    NM_SALA VARCHAR(100) UNIQUE NOT NULL,
    FOREIGN KEY (ID_USUARIO) REFERENCES TB_USUARIO(ID_USUARIO)
);

-- Tabela de participantes
CREATE TABLE TB_PARTICIPANTE (
    ID_PARTICIPANTE INT PRIMARY KEY AUTO_INCREMENT,
    ID_SALA INT,
    ID_USUARIO INT,
    UNIQUE KEY (ID_SALA, ID_USUARIO),
    FOREIGN KEY (ID_SALA) REFERENCES TB_SALA(ID_SALA),
    FOREIGN KEY (ID_USUARIO) REFERENCES TB_USUARIO(ID_USUARIO)
);

-- Tabela de mensagens
CREATE TABLE TB_MENSAGEM (
    ID_MENSAGEM INT PRIMARY KEY AUTO_INCREMENT,
    ID_SALA INT,
    ID_USUARIO_ENVIO INT,
    ID_USUARIO_PARA INT NULL,
    NM_USUARIO_PARA VARCHAR(100) NULL,
    DS_MENSAGEM TEXT NOT NULL,
    DT_MENSAGEM TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    TP_MENSAGEM VARCHAR(20) DEFAULT 'mensagem',
    FOREIGN KEY (ID_SALA) REFERENCES TB_SALA(ID_SALA),
    FOREIGN KEY (ID_USUARIO_ENVIO) REFERENCES TB_USUARIO(ID_USUARIO),
    FOREIGN KEY (ID_USUARIO_PARA) REFERENCES TB_USUARIO(ID_USUARIO)
);
Inicie o servidor backend:

npm start
# ou para desenvolvimento com nodemon:
npm run dev
Frontend
Navegue para o diretório frontend:

cd ../frontend
Instale as dependências:

npm install
# ou
yarn install
Configure o ambiente:

Verifique se o backend está em execução na porta correta (padrão: 3001)
Ajuste a URL da API em src/service/api.js se necessário
Inicie o servidor de desenvolvimento:

npm start
# ou
yarn start
Abra http://localhost:3000 no seu navegador.

📡 API Endpoints
Autenticação e Usuários
POST /api/users/register - Cadastra um novo usuário

Body: { "name": "Nome", "email": "email@example.com", "password": "senha123" }
POST /api/users/login - Realiza login

Body: { "email": "email@example.com", "password": "senha123" }
GET /api/users - Lista todos os usuários

PUT /api/users/:id - Atualiza um usuário

Body: { "name": "Novo Nome" }
POST /api/users/reset-password - Redefine a senha de um usuário

Body: { "id": 1, "currentPassword": "senha-atual", "newPassword": "nova-senha" }
Salas
POST /api/rooms - Cria uma nova sala

Body: { "name": "Nome da Sala", "userId": 1 }
GET /api/rooms - Lista todas as salas

GET /api/rooms/:id - Obtém detalhes de uma sala específica

GET /api/rooms/user/:userId - Lista salas de um usuário

Participantes
POST /api/rooms/participants - Adiciona um participante a uma sala

Body: { "roomId": 1, "userId": 1 }
DELETE /api/rooms/participants/:roomId/:userId - Remove participante de uma sala

GET /api/rooms/:roomId/participants - Lista participantes de uma sala

Mensagens
POST /api/messages - Envia uma mensagem

Body: { "senderId": 1, "roomId": 1, "content": "Texto da mensagem", "receiverId": null }
GET /api/messages/room/:roomId - Lista mensagens de uma sala

GET /api/messages/direct/:senderId/:receiverId - Lista mensagens diretas entre dois usuários

PUT /api/messages/:id - Atualiza uma mensagem

Body: { "content": "Novo texto da mensagem" }
DELETE /api/messages/:id - Remove uma mensagem

📱 Responsividade
A aplicação foi projetada para funcionar bem em diferentes dispositivos:

Desktop: Layout completo com todas as funcionalidades visíveis
Tablet: Adaptação de elementos para telas médias
Mobile: Reorganização do layout para telas pequenas
Formulário de chat e área de mensagens em orientação vertical
Botões e controles redimensionados para toque
Interface simplificada para melhor usabilidade em dispositivos móveis
🚀 Processo de Deploy
Frontend
cd frontend
npm run build
# ou
yarn build
Backend
cd backend
npm run build
Ambientes de hospedagem recomendados
Frontend:
Netlify, Vercel, GitHub Pages, AWS S3 + CloudFront, Firebase Hosting
Backend:
Heroku, AWS EC2, Google Cloud Run, Azure App Service, Digital Ocean Droplets
Configuração de produção
Ajuste variáveis de ambiente para ambiente de produção
Configure conexão segura entre frontend e backend
Otimize assets estáticos e configure regras de cache
Implemente monitoramento de erros e performance
🤝 Contribuição
Contribuições são muito bem-vindas! Para contribuir:

Faça um fork do projeto
Crie uma branch para sua feature: git checkout -b feature/nova-funcionalidade
Faça commit das alterações: git commit -m 'feat: Adiciona nova funcionalidade'
Envie para o GitHub: git push origin feature/nova-funcionalidade
Abra um Pull Request
Boas práticas
Siga o padrão de commits convencionais (feat, fix, docs, style, refactor, etc.)
Adicione testes para novas funcionalidades
Mantenha a documentação atualizada
Verifique se o código passa nos linters antes de enviar
📊 Modelos de Dados
Usuário
{
    ID_USUARIO: Number,        // Identificador único do usuário
    NM_USUARIO: String,        // Nome/apelido do usuário
    DS_EMAIL: String,          // Email (usado para login)
    DS_SENHA: String           // Senha de acesso
}
Sala
{
    ID_SALA: Number,           // Identificador único da sala
    ID_USUARIO: Number,        // Identificador do criador da sala
    NM_SALA: String            // Nome da sala
}
Participante
{
    ID_PARTICIPANTE: Number,   // Identificador único da participação
    ID_SALA: Number,           // Identificador da sala
    ID_USUARIO: Number         // Identificador do usuário participante
}
Mensagem
{
    ID_MENSAGEM: Number,       // Identificador único da mensagem
    ID_SALA: Number,           // Sala onde a mensagem foi enviada
    ID_USUARIO_ENVIO: Number,  // Usuário que enviou a mensagem
    ID_USUARIO_PARA: Number,   // Destinatário (null para todos)
    NM_USUARIO_PARA: String,   // Nome do destinatário (opcional)
    DS_MENSAGEM: String,       // Conteúdo da mensagem
    DT_MENSAGEM: Date,         // Data e hora do envio
    TP_MENSAGEM: String        // Tipo da mensagem (mensagem, entrada)
}
📚 Recursos Adicionais
React Documentation - Documentação oficial do React
React Router Documentation - Guia de navegação
Express Documentation - Framework para Node.js
MySQL Documentation - Banco de dados relacional
Axios Documentation - Cliente HTTP
React Toastify Documentation - Sistema de notificações
📝 Licença
Este projeto está licenciado sob a Licença MIT. Veja o arquivo LICENSE para mais detalhes.

Desenvolvido com 💜 pelo grupo Esquemas d@ Bolívi@
