# Bem vindo a SmileAPI a melhor opcão para escalabilidade e estabilidade em integracoes com WhatsApp 

## Introdução

Esta API foi desenvolvida para fornecer uma solução escalável e de alta performance para integração com o WhatsApp. Ela é ideal para empresas que precisam atender a grandes demandas com eficieencia e estabilidade e confiabilidade com seus clientes através do WhatsApp, garantia de estabilidade, isolamento e alta disponibilidade.

### Escalabilidade e Isolamento
A API é implementada em um ambiente Kubernetes, onde cada instância do serviço é executada de forma isolada em seu próprio POD. Esse modelo garante estabilidade e evita interferências entre instâncias.

### Baixo Consumo
Cada instancia criada na API tem um consumo extremamente baixo entre 5Mb a 20Mb sendo possivel com isso ter centenas ou ate milhares de instancias ativas em uma unica VPS, e por usar clusterizda com kubernetes é ainda possivel adicionar mais VPS ao cluster se necessario.

### Alta Performance em Tempo Real
Utilizamos tecnologia de WebSockets para comunicação instantânea e eficiente com o WhatsApp, proporcionando baixa latência e alta confiabilidade.

### Mensageria Garantida com RabbitMQ
Todas as requisições de envio de mensagens passam por uma fila de processamento no RabbitMQ. Isso garante que nenhuma mensagem seja perdida, mesmo em situações de indisponibilidade momentânea da API. Se um envio falhar no momento da requisição, ele será automaticamente processado assim que o serviço estiver disponível novamente.

### Compatibilidade Total com a API Oficial da Meta
Os endpoints e parâmetros seguem exatamente o padrão da API Oficial da Meta, garantindo integração simplificada para desenvolvedores e compatibilidade total com aplicações já existentes.

### Documentação Completa
Disponibilizamos uma documentação clara e detalhada para facilitar a implementação e uso da API.

## Requisitos para Instalação

Para instalar e configurar a API, você precisará de:

- **VPS com Ubuntu Server**: Recomendamos pelo menos 4GB de RAM e 4 cores de CPU, mas para melhor desempenho, sugerimos 8GB de RAM.
- **Três Subdomínios**: Todos devem apontar para o IP da sua VPS.
  - **Domínio principal**: Para acessar o painel da plataforma (ex.: `wappi.io`).
  - **Domínio para documentação e requisições da API**: Ex.: `api.wappi.io`.
  - **Domínio para backend**: Ex.: `backend.wappi.io`.

### CAPTCHA - Turnstile da Cloudflare

A plataforma utiliza o Turnstile da Cloudflare como solução de CAPTCHA para proteger formulários e garantir a segurança contra bots.

- **Configuração do Turnstile**:
  1. Acesse sua conta na Cloudflare.
  2. Navegue até a opção **Turnstile**.
  3. Adicione o domínio principal da plataforma (ex.: `wappi.io`).
  4. Gere as seguintes chaves:
     - **Site Key**: Chave pública que será usada no frontend da aplicação.
     - **Secret Key**: Chave privada que será usada no backend para validação.

## Instalação

Siga os passos abaixo para configurar e instalar a API:

### 1. Configuração do Turnstile na Cloudflare

1. Acesse o painel da Cloudflare.
2. Navegue até a seção **Turnstile**.  
 ![cloudflare](https://github.com/user-attachments/assets/e388059a-86eb-4092-9833-395ae1645e96)

3. Clique em **Add Widget**.
 ![image](https://github.com/user-attachments/assets/832360c1-8d05-4415-8c15-24259cc1d4a5)

4. Defina um nome para o widget , clique em add hostname e selecione o dominio que ira usar na API, em Widget Mode selecione a opcao Non-interactive e clique em Create
  ![image](https://github.com/user-attachments/assets/2ca975e7-9bf8-44aa-a717-372135d9d240)

5. Copie as chaves gerados pois as mesmas serao necessarias **Site Key** e **Secret Key**.


### 2. Acesso à VPS via SSH

1. Acesse sua VPS utilizando SSH:
   ```bash
   ssh usuario@ip_da_vps
   ```

2. Execute o comando abaixo para iniciar a instalação automática da API:
   ```bash
   /bin/bash -c "$(curl -fsSL https://deploy.wappi.io)"
   ```

Siga as Instruçoes do Shell Script:
![image](https://github.com/user-attachments/assets/60b0863b-d237-4fb5-9d56-a955546acab1)

Apos concluido o processo de deploy dos micro servicos a API estara disponivel para uso , acesse o Painel no dominio que configurou

Para gerenciamento da API e monitoranto do cluster recomendamos o uso da ferramenta ***Lens Desktop****  
Faca o download em https://k8slens.dev/download

Apos baixar, instalar e criar uma conta voce deve adicionar a chave de acesso do cluster no Lens, esse arquivo foi gerado na instalacao da API com o nome ***kubeconfig.yaml***
Acesse a VPS e copie esse arquivo para sua maquina local , existem diversas formas para se copiar esse arquivo da VPS para sua maquina , escolha a forma de sua preferencia
como exemplo usando scp ou FTP etc....

Uma vez copiado o arquivo no Lens clique com o botao direito do mouse em Local KubeConfigs e selecione o arquivo kubeconfig.yaml que baixou da VPS
![image](https://github.com/user-attachments/assets/d3f755b9-bbe4-480b-b606-ef8c9783ecce)


Agora vc tem acesso total ao cluster da API
![image](https://github.com/user-attachments/assets/3da9c966-05f2-4b16-ab8f-fe1766c75d0d)

Va ate PODs e acompanhe a criacao das instacias, monitore logs, veja consumo de memoria e CPU etc.....
![image](https://github.com/user-attachments/assets/03fac0ba-bee0-418f-ae37-65bef5b88ad7)


## Suporte

Lembrando que essa instalacao tem o objetivo de demostracao da plataforma para que possa usar e conhecer, ***NAO SE TRATA DE UM PRODUTO OPENSOURCE***

PARA CONTRATAR A API ENTRE EM CONTATO COMIGO NO WHATSAPP 43 996611437

