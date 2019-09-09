# Trabalho - Wireshark

> Estou enviando pelo GitHub, porque o tamanho total dos arquivos (capturados pelo Wireshark e os prints) excediam o tamanho máximo de upload do SGA

## HTTP

### 1. A Interação Básica GET/Resposta do HTTP

#### 1. O seu navegador executa HTTP 1.0, 1.1 ou 2.0? Qual a versão de HTTP do servidor?
HTTP 1.1

HTTP 1.1

![Responsta 1 (1)](./img/trabalho.wireshark.http.1.01.a.png)
![Responsta 1 (2)](./img/trabalho.wireshark.http.1.01.b.png)

#### 2. Quais linguagens (se alguma) o seu navegador indica que pode aceitar ao servidor?
Espanhol, Inglês e Português.

![Responsta 2](./img/trabalho.wireshark.http.1.02.png)

#### 3. Qual o endereço IP do seu computador? E do servidor gaia.cs.umass.edu?
```
192.168.15.7
128.119.245.12
```

![Responsta 3](./img/trabalho.wireshark.http.1.03.png)

#### 4. Qual o código de status retornado do servidor para o seu navegador?
```
200
```

![Responsta 4](./img/trabalho.wireshark.http.1.04.png)

#### 5. Quando o arquivo em HTML que você baixou foi modificado no servidor pela última vez?
Domingo, 8 de setembro de 2019 às 05:59:01 (GMT)

![Responsta 5](./img/trabalho.wireshark.http.1.05.png)

#### 6. Quantos bytes de conteúdo são retornados ao seu navegador?
128 bytes

![Responsta 6](./img/trabalho.wireshark.http.1.06.png)

#### 7. Inspecionando os dados na janela de conteúdo do pacote, você vê algum cabeçalho dentro dos dados que não são exibidos na janela de listagem de pacotes? Caso a resposta seja afirmativa, indique um.
Não

### 2. A Interação HTTP GET Condicional/Resposta

#### 8. Inspecione o conteúdo da primeira mensagem HTTP GET do seu navegador para o servidor. Você vê uma linha `IF-MODIFIED-SINCE`?
Não

![Responsta 8](./img/trabalho.wireshark.http.2.08.png)

#### 9. Inspecione o conteúdo da resposta do servidor. O servidor retornou explicitamente o conteúdo do arquivo? Como você pode dizer isso?
Não. Não existe o item `Line-based text data`, como nos pacotes analizados na seção **1. A Interação Básica GET/Resposta do HTTP** e também não existe o campo `File data` informando o tamanho do arquivo recebido.

![Responsta 9](./img/trabalho.wireshark.2.09.png)

#### 10. Agora inspecione o conteúdo da segunda mensagem HTTP GET do seu navegador para o servidor. Você vê uma linha `IF-MODIFIED-SINCE`? Caso a resposta seja afirmativa, qual informação segue o cabeçalho `IF-MODIFIED-SINCE`?
Sim. Domingo, 8 de setembro de 2019 às 05:59:01 (GMT), que é a data da última modificação do arquivo.

![Responsta 10](./img/trabalho.wireshark.http.2.10.png)

#### 11. Qual é o código de status e a frase retornada do servidor na resposta à segunda mensagem HTTP GET? O servidor retornou explicitamente o conteúdo do arquivo? Explique.
```
Status code: 304
Response phrase: Not modified
```

![Responsta 11](./img/trabalho.wireshark.http.2.11.png)

### 3. Baixando Documentos Longos

### 12. Quantas mensagens HTTP GET foram enviadas pelo seu navegador?
1 mensagem HTTP

![Responsta 12](./img/trabalho.wireshark.http.3.12.png)

#### 13. Quantos segmentos TCP foram necessários para carregar a resposta?
4 segmentos TCP

![Responsta 13](./img/trabalho.wireshark.http.3.13.png)

#### 14. Qual é o código de status e a frase associada com a resposta à mensagem HTTP GET?
```
Status code: 200
Response phrase: OK
```

![Responsta 14](./img/trabalho.wireshark.http.3.14.png)

#### 15. Há alguma linha de status HTTP nos segmentos TCP associados a esta transferência?
Não.

![Responsta 15](./img/trabalho.wireshark.http.3.15.png)

### 4. Documentos HTML com Objetos Incluídos

#### 16. Quantas mensagens HTTP GET foram enviadas pelo seu navegador? Para quais endereços na Internet estas mensagens foram enviadas?
3 mensagens HTTP

![Responsta 16](./img/trabalho.wireshark.http.4.16.png)

#### 17. Você consegue dizer se o seu navegador baixou as duas imagens em sequência, ou se foram baixadas dos dois locais distintos em paralelo? Explique.
Foram baixadas em sequência. A primeira imagem (pearson.png) terminou de baixar antes que a segunda (cover_5th_ed.jpg) fosse requisitada.

![Responsta 17](./img/trabalho.wireshark.http.4.17.png)

### 5. Autenticação HTTP

#### 18. Qual é a resposta do servidor (código de status e frase) para o primeira mensagem HTTP GET do seu navegador?
```
Status code: 401
Response phrase: Unauthorized
```

![Responsta 18](./img/trabalho.wireshark.http.5.18.png)

#### 19. Quando o seu navegador envia a mensagem HTTP GET pela segunda vez, qual o novo campo que está incluído na mensagem?
```
Authorization: Basic d2lyZXNoYXJrLXN0dWRlbnRzOm5ldHdvcms=
    Credentials: wireshark-students:network
```

![Responsta 19](./img/trabalho.wireshark.http.5.19.png)

## DNS

#### 1. Obtenha o endereço IP de um servidor web na Ásia;
```
58.229.6.225
```

![Resposta 1](./img/trabalho.wireshark.dns.1.01.png)

#### 2. Determine os servidores DNS autoritários para uma universidade na Europa;

```
auth5.dns.ox.ac.uk.
dns1.ox.ac.uk.
dns2.ox.ac.uk.
dns0.ox.ac.uk.
ns2.ja.net.
auth6.dns.ox.ac.uk.
auth4.dns.ox.ac.uk.
```

![Resposta 2](./img/trabalho.wireshark.dns.1.02.png)

#### 3. Utilize um dos servidores DNS obtido na questão 2 e consulte pelo endereço IP do Portal Office365.

Nenhum ip foi encontrado.

![Resposta 3](./img/trabalho.wireshark.dns.1.03.png)

#### 4. Localize as mensagens de solicitação e resposta DNS. Foram enviadas com TCP ou UDP?

UDP

![Resposta 4](./img/trabalho.wireshark.dns.3.04.png)

#### 5. Qual é a porta destino para a mensagem de consulta DNS? Qual é a porta fonte da mensagem de resposta DNS?

```
53
```

![Resposta 5](./img/trabalho.wireshark.dns.3.05.png)

#### 6. A qual endereço IP a mensagem de consulta DNS é enviada? Utilize ipconfig para verificar qual é o endereço IP do seu servidor DNS local. Estes endereços são os mesmos?

```
8.8.8.8
```

![Resposta 6](./img/trabalho.wireshark.dns.3.06.png)

#### 7. Examine a mensagem de consulta DNS. Qual o campo "type" desta mensagem? A mensagem de consulta contém algum campo "answer"?

`A` e `AAAA`

![Resposta 7](./img/trabalho.wireshark.dns.3.07.a.png)
![Resposta 7](./img/trabalho.wireshark.dns.3.07.b.png)

#### 8. Examine a mensagem de resposta DNS. Quantos campos com "answer" existem? O que há em cada uma destas mensagens?

```
#7:  1 resposta
#9:  1 resposta
#24: 3 resposta
#27: 3 resposta
```

![Resposta 8 (1)](./img/trabalho.wireshark.dns.3.08.a.png)
![Resposta 8 (2)](./img/trabalho.wireshark.dns.3.08.b.png)
![Resposta 8 (3)](./img/trabalho.wireshark.dns.3.08.c.png)
![Resposta 8 (4)](./img/trabalho.wireshark.dns.3.08.d.png)

#### 9. Considere o segmento TCP SYN subsequente enviado pelo seu host. O endereço IP de destino do pacote SYN corresponde a algum dos endereços IP fornecidos na mensagem de resposta DNS?

Não.

![Resposta 9](./img/trabalho.wireshark.dns.3.09.png)

#### 10. A página web visitada contém imagens. Antes de recuperar cada imagem, o host realiza novas consultas DNS?

Não.

![Resposta 10](./img/trabalho.wireshark.dns.3.10.png)

#### 11. Qual é a porta destino para a mensagem de consulta DNS? Qual é a porta fonte para a mensagem de resposta DNS?

```
Porta de consulta: 53
Porta de resposta: 57394
```

![Resposta 11](./img/trabalho.wireshark.dns.3.11.png)

#### 12. A qual endereço IP a mensagem de consulta DNS está endereçada? Este endereço é o de algum dos seus servidores DNS locais?

```
8.8.8.8
```

![Resposta 12](./img/trabalho.wireshark.dns.3.12.png)

#### 13. Examine a mensagem de consulta DNS. Qual o campo "type" que há nela? A mensagem de consulta contém algum campo "answer"?

Tipo A

![Resposta 13](./img/trabalho.wireshark.dns.3.13.png)

#### 14. Examine a mensagem de resposta DNS. Quantos campos com "answer" existem? O que há em cada uma destas respostas?

```
#19: 3 respostas
#22: 2 respostas
```

![Resposta 14 (1)](./img/trabalho.wireshark.dns.3.14.a.png)
![Resposta 14 (2)](./img/trabalho.wireshark.dns.3.14.b.png)

#### 16. A qual endereço IP a mensagem de consulta DNS está endereçada? Este endereço é o de algum dos seus servidores DNS locais?

```
8.8.8.8
```

![Resposta 16](./img/trabalho.wireshark.dns.3.16.png)

#### 17. Examine a mensagem de consulta DNS. Qual o campo "type" que há nela? A mensagem de consulta contém algum campo "answer"?

Tipo NS

![Resposta 17](./img/trabalho.wireshark.dns.3.17.png)

#### 18. Examine a mensagem de resposta DNS. Quais servidores DNS da PUC Minas são fornecidos na resposta? Esta mensagem de resposta também fornece os endereços IP dos servidores DNS da PUC Minas?

```
server02.pucminas.br
ns.embratel.net.br
ns.pucminas.br
```

![Resposta 18](./img/trabalho.wireshark.dns.3.18.png)

#### 20. A qual endereço IP a mensagem de consulta DNS está endereçada? Este endereço é o de algum dos seus servidores DNS locais? Caso contrário, qual o host para este endereço IP?

Não. `dns.google.com`

![Resposta 20](./img/trabalho.wireshark.dns.3.20.png)

#### 21. Examine a mensagem de consulta DNS. Qual o campo "type" que há nela? A mensagem de consulta contém algum campo "answer"?

Tipo A. Não há nenhum campo "answer".

![Resposta 21](./img/trabalho.wireshark.dns.3.21.png)

#### 22. Examine a mensagem de resposta DNS. Quantos campos com "answer" existem? O que há em cada uma destas respostas?

1 campo "answer".

![Resposta 22](./img/trabalho.wireshark.dns.3.22.png)