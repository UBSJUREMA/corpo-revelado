# Corpo Revelado — versão portátil

O projeto contém a interface React e o servidor Node.js/Express. Não foram encontradas chamadas para a página original. As chamadas de IA usam o Gemini; as fontes visuais usam o Google Fonts.

## Executar no computador

Instale Node.js 22 ou superior. Extraia este ZIP e abra um terminal na pasta extraída:

    npm install
    npm run build
    npm start

Abra http://localhost:3000. Para editar com atualização automática, use npm run dev.

## Gemini (opcional para o modo básico)

Sem chave, o código original gera respostas por modelos de texto predefinidos. Esse modo não interpreta imagens e vídeos e não equivale à geração por IA.

Para ativar Gemini, crie .env.local na pasta do projeto:

    GEMINI_API_KEY=sua_chave

Reinicie o servidor. Em hospedagem, configure GEMINI_API_KEY nas variáveis privadas do servidor. Não coloque a chave em código de navegador nem publique o arquivo .env.local.

Não foi fornecida uma chave: autenticação, disponibilidade dos modelos e geração real por Gemini não foram testadas. Eventuais custos e cotas da API são separados da hospedagem.

## Publicar fora do AI Studio

Este projeto precisa de hospedagem com suporte a servidor Node.js; hospedar somente os arquivos estáticos da pasta dist não ativa as rotas /api.

Configuração de um serviço Node.js:

- Instalação: npm install
- Build: npm run build
- Inicialização: npm start
- Health check: /api/health
- Variáveis: NODE_ENV=production; GEMINI_API_KEY se desejar IA
- Porta: o servidor respeita a variável PORT da hospedagem; padrão 3000

O cadastro de faturamento do Google Cloud usado para publicar pelo AI Studio não faz parte dessa instalação. A hospedagem escolhida terá suas próprias condições. Nenhum site público foi criado nesta etapa.

## Ajustes realizados

- Leitura de .env.local e .env, alinhada às instruções de configuração.
- Porta configurável por PORT.
- npm start ativa a versão de produção também no Windows.

## Verificação

TypeScript e compilação de produção passaram. Servidor testado na porta 3187: página inicial HTTP 200, health check sem chave, seis sugestões, oito prompts pelo modo offline-template e saudação do chat.

O conteúdo e as regras editoriais do projeto original foram preservados. Não houve validação das alegações de saúde presentes nos textos.
