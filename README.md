<h1>Atividade 4 - Orquestração com Swarm e Compose</h1>

<h2>Passo 1: Iniciando o Swarm</h2>

<p>Execute o comando abaixo para iniciar o Swarm:</p>

<pre><code>docker swarm init</code></pre>

<h2>Passo 2: Iniciando o serviço no Swarm</h2>

<p>Execute o seguinte comando para iniciar o serviço no Swarm:</p>

<pre><code>docker service create --name registry --publish published=5000,target=5000 registry:2</code></pre>

<h2>Passo 3: Verificando o status dos serviços</h2>

<p>Para verificar o status dos serviços, utilize o seguinte comando:</p>

<pre><code>docker service ls</code></pre>

<h2>Passo 4: Verificando se o serviço está funcionando</h2>

<p>Para verificar se o serviço está funcionando corretamente, execute o seguinte comando:</p>

<pre><code>curl http://localhost:5000/v2/</code></pre>

<h2>Passo 5: Criando os arquivos do aplicativo</h2>

<p>Siga a documentação do Docker para criar os arquivos: https://docs.docker.com/engine/swarm/stack-deploy/ .</p>

<h2>Passo 6: Testando o aplicativo</h2>

<p>Execute o seguinte comando para testar o aplicativo:</p>

<pre><code>docker-compose up -d</code></pre>

<p>ou</p>

<pre><code>docker-compose up</code></pre>

<h2>Passo 7: Verificando se o aplicativo está funcionando</h2>

<p>Utilize o comando a seguir para verificar se o aplicativo está em execução:</p>

<pre><code>docker-compose ps</code></pre>

<h2>Passo 8: Testando a porta escolhida</h2>

<p>Para testar a porta escolhida para o aplicativo, utilize o seguinte comando:</p>

<pre><code>curl http://localhost:8000</code></pre>

<h2>Passo 9: Desligando o aplicativo</h2>

<p>Para desligar o aplicativo, execute o comando abaixo:</p>

<pre><code>docker-compose down --volumes</code></pre>

<h2>Passo 10: Enviando a imagem para o serviço</h2>

<p>Utilize o comando a seguir para enviar a imagem para o serviço:</p>

<pre><code>docker-compose push</code></pre>

<h2>Passo 11: Fazendo o deploy dos arquivos para os integrantes do Swarm</h2>

<p>Para fazer o deploy dos arquivos para os integrantes do Swarm, utilize o comando abaixo:</p>

<pre><code>docker stack deploy --compose-file docker-compose.yml stackdemo</code></pre>

<h2>Passo 12: Verificando se os serviços estão corretos</h2>

<p>Para verificar se os serviços estão corretamente configurados, execute o seguinte comando:</p>

<pre><code>docker stack services stackdemo</code></pre>

<h2>Passo 13: Testando na máquina líder (leader)</h2>

<p>Para testar na máquina líder (leader), utilize o comando a seguir:</p>

<pre><code>curl http://localhost:8000</code></pre>

<h2>Passo 14: Testando nas máquinas workers</h2>

<p>Para testar nas máquinas workers, execute o comando abaixo, substituindo "address-of-other-node" pelo endereço da máquina worker que você deseja testar:</p>

<pre><code>curl http://address-of-other-node:8000</code></pre>

<p>Certifique-se de substituir "address-of-other-node" pelo endereço da máquina worker que você deseja testar.</p>

<p>Lembre-se de adaptar os comandos e arquivos de acordo com as suas necessidades e configurações.</p>
