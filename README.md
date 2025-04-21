Táxi Missões - Aplicativo de Transporte
Este projeto é um sistema de aplicativo de transporte de táxi para motoristas e passageiros, com funcionalidades de solicitação de corridas, painel para motoristas, e integração com o Firebase para gerenciamento de dados em tempo real.

Funcionalidades
Passageiro:
Solicitar Corrida: O passageiro pode solicitar uma corrida informando seu nome e destino.

Mapa Interativo: Exibe o mapa com a localização do passageiro e permite ao motorista visualizá-lo.

Motorista:
Login de Motorista: Os motoristas fazem login para acessar o painel de corridas.

Aceitar Corrida: O motorista pode visualizar corridas solicitadas e aceitar ou recusar.

Mapa Interativo: Mostra a localização das corridas solicitadas em tempo real.

Como Usar
Requisitos
Firebase: O projeto utiliza o Firebase para autenticação e banco de dados em tempo real. Siga as etapas abaixo para configurar o Firebase:

Crie um projeto no Firebase.

Habilite o Firebase Authentication para login dos motoristas (e-mail/senha).

Habilite o Firebase Realtime Database para armazenar as corridas e status.

API Key do Firebase: Copie a configuração do Firebase no painel do seu projeto e insira as credenciais no arquivo admin.html e login_motorista.html:

javascript
Copiar
Editar
const firebaseConfig = {
  apiKey: "SUA_API_KEY",
  authDomain: "SEU_DOMINIO.firebaseapp.com",
  databaseURL: "https://SEU_DOMINIO-default-rtdb.firebaseio.com",
  projectId: "SEU_PROJETO",
  storageBucket: "SEU_BUCKET.appspot.com",
  messagingSenderId: "ID_MENSAGEM",
  appId: "SEU_APP_ID"
};
Passo a Passo para Configuração
Firebase Configuration: Insira as credenciais do Firebase em todos os arquivos relevantes (como admin.html e login_motorista.html).

Hospedagem do App: Você pode hospedar este aplicativo em plataformas como Firebase Hosting ou GitHub Pages.

Instalar Dependências:

Este projeto utiliza o Leaflet.js para renderizar o mapa.

O Firebase é utilizado para autenticação e banco de dados em tempo real.

Certifique-se de incluir os links do Firebase e do Leaflet no cabeçalho de cada página HTML.

Fluxo do App
Passageiro acessa index.html, preenche o nome e destino, e a solicitação de corrida é registrada no Firebase.

Motorista faz login na página login_motorista.html com e-mail e senha.

Após login, o motorista é redirecionado para admin.html, onde pode ver as corridas solicitadas e aceitá-las.

O status da corrida é atualizado em tempo real no Firebase e também é refletido no painel do motorista.

Estrutura de Arquivos
pgsql
Copiar
Editar
├── index.html             # Página do Passageiro (Solicitação de Corrida)
├── login_motorista.html   # Página de Login do Motorista
├── admin.html             # Painel do Motorista (Visualização das Corridas)
├── script.js              # Scripts JavaScript para controle da interface
├── firebase_config.js     # Arquivo com as configurações do Firebase (opcional)
└── README.md              # Este arquivo de documentação
Contribuições
Se você deseja contribuir para este projeto:

Faça um fork deste repositório.

Crie uma branch com sua feature ou correção (git checkout -b minha-feature).

Faça commit das suas mudanças (git commit -am 'Adiciona nova funcionalidade').

Envie para o repositório remoto (git push origin minha-feature).

Abra um Pull Request.

Licença
Este projeto está licenciado sob a MIT License.
