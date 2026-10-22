# projetoExpress
Site de streaming- Cronos
# CRONOS — Streaming de História

**Tema:** História mundial e do Brasil em um só lugar.

**Slogan:** *O passado nunca esteve tão perto.*

**Projeto Express — SENAI São Paulo · Félix Guisard · Técnico em Desenvolvimento de Sistemas · 2026**

## Integrantes
- Ana Beatriz
- Lorena Sacchi
- Bianca Oliveira
- Lavinia Hermenegildo

## Tecnologias utilizadas
O site foi feito com HTML, CSS, JavaScript e PHP, utilizamos o MySQL para armazenar os dados. Para criar e gerenciar o banco de dados, utilizamos o phpMyAdmin. O projeto foi feito sem o uso de frameworks.

## Vídeos e resumos
Cada conteúdo do CRONOS possui um resumo próprio, feito para ajudar o usuário a entender melhor o assunto antes de assistir ao vídeo. Ao abrir um conteúdo, o vídeo correspondente do YouTube aparece na própria página, sem precisar acessar outro site para encontrar explicações.

Os resumos ficam no arquivo `assets/data.js`, e os códigos dos vídeos estão organizados no objeto `VIDEOS`, no mesmo arquivo. Caso seja necessário trocar um vídeo, basta copiar o código que aparece depois de `v=` no link do YouTube.

Se algum conteúdo estiver sem um vídeo definido, o sistema pode procurar um automaticamente usando a YouTube Data API. Para isso, é necessário configurar a chave `YOUTUBE_KEY` no arquivo `config.php`. O vídeo encontrado fica salvo no banco de dados. Como o projeto já possui os códigos dos 15 vídeos cadastrados, essa configuração é opcional.

## Como executar o projeto no XAMPP
1. Copie a pasta `chronos` para dentro da pasta `htdocs`.
2. Abra o phpMyAdmin e importe o arquivo `db.sql` para criar as tabelas do banco de dados.
3. Abra o arquivo `config.php` e configure os dados de acesso ao banco, a chave `RESEND_KEY` e o e-mail `DONO_EMAIL`, que deve ser o e-mail da conta Resend. A chave `YOUTUBE_KEY` só precisa ser configurada caso queira utilizar a busca automática de vídeos.
4. Inicie o Apache e o MySQL no XAMPP.
5. Acesse o endereço `http://localhost/chronos/` pelo navegador.

Ao entrar no site, o usuário verá uma página inicial com uma apresentação do CRONOS. No menu, poderá escolher entre entrar em uma conta existente ou realizar um cadastro. Depois de fazer login ou se cadastrar, será direcionado ao catálogo de conteúdos históricos.

## Funcionalidades do site
O CRONOS foi pensado para facilitar o acesso à História de uma forma simples e organizada. Entre as principais funcionalidades estão:

- **Página inicial:** apresenta o site e sua proposta, com as opções de entrar e cadastrar.
- **Cadastro e login:** permite criar uma conta e acessar o catálogo usando uma sessão.
- **Catálogo protegido:** os conteúdos só podem ser acessados após o login, por meio da página `catalogo.php`.
- **Categorias históricas:** o catálogo possui cinco categorias, cada uma com três conteúdos, totalizando 15 assuntos.
- **Resumos e vídeos:** cada conteúdo apresenta uma explicação breve e um vídeo relacionado ao tema.
- **Busca e filtros:** ajudam o usuário a encontrar conteúdos sem precisar recarregar a página.
- **Favoritos:** permite salvar conteúdos favoritos de cada usuário no banco de dados.
- **Redefinição de senha:** conta com uma funcionalidade simulada para recuperação de acesso.
- **Notificação por e-mail:** a cada novo cadastro, o responsável pelo projeto recebe uma mensagem por meio do serviço Resend.

Para aumentar a segurança, as senhas são armazenadas utilizando `password_hash`, evitando que sejam salvas diretamente em texto puro no banco de dados. 
