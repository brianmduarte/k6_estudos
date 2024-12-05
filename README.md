
# Estudo utilizando o K6 para Testes de Performance

**1. Pré-requisitos**

* IDE de desenvolvimento (VS code ou outro de sua preferência)
* Sistema operacional: Ubuntu 14. ou superior

**2. Instalação**

1º
``bash
sudo gpg --no-default-keyring --keyring /usr/share/keyrings/k6-archive-keyring.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys C5AD17C747E3415A3642D57D77C6C491D6AC1D69
echo
`` 

2º
``
"deb [signed-by=/usr/share/keyrings/k6-archive-keyring.gpg] https://dl.k6.io/deb stable main" | sudo tee /etc/apt/sources.list.d/k6.list
``

3º
``
sudo apt-get update
``

4º
``
sudo apt-get install k6
``

Obs: execute uma linha de comando por vez

**3. Criando o primeiro Teste**

Crie uma pasta com o nome desejado para hospedagem do k6:

``bash
mkdir C:/Testes/k6
``

Na raiz do projeto (/k6), crie um arquivo JavaScript chamado script.js:

``bash
touch script.js
``

**4. Abrindo o projeto**

Ainda no terminal, execute o comando abaixo para abrir a IDE de desenvolvimento

``bash
code .
``

**5. Criando um teste base com o k6**

Copie e cole o script abaixo no seu arquivo script.js

```bash

import http from 'k6/http';
import { sleep } from 'k6';

export default function () {
  http.get('https://test.k6.io');
  sleep(1);
}
```

Neste código, estamos importando o http para realizar as requisições dos 
testes. O sleep é utilizado para aguardar um determinado período de tempo, 
e depois criamos uma função 'default' que fará uma simples requisição do 
tipo get na API do k6.

**6. Executando o teste de script.js**

``bash
k6 run script.js
``



