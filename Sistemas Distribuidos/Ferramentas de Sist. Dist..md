# Ferramentas de Sist. Dist.
Como eles precisam de algum meio de comunicação, nada mais óbvio do que utilizar algum meio para que mensagens possam ser trocadas.

## Interface de SOCKET
- API POSIX padrão de comunicação que fica acima da camada de transporte de rede.
- Sockets são o ponto final da comunicação, quando estamos na barreira entre transporte (mantido pelo SO) e uso no app (modificável pelo desenvolvedor).
- Na parte da API do SO, o SOCKET usa TCP para troca de mensagens por sistemas, mas pode usar UDP!

## Interconectando dispositivos via TCP
Temos dois lados da conexão, o lado **passivo** e o lado **ativo**. O primeiro _se prepara e recebe as mensagens_, enquanto o segundo _se conecta _ para enviar mensagens, mas também pode recebê-las

### Lado passivo
- Via a interface socket, fazemos um _bind_ para prendermos nossos ouvidos à um endereço e porta.
- Com _listen_, ouvimos por novas conexões.
- Quando uma nova conexão vem, aceitamos ela com _accept_.
- O lado passivo começa ouvindo com _recv_...
- ...e depois pode mandar mensagens com _send_!
- Algum comando do lado ativo fecha a conexão...
- ... e paramos o serviço

### Lado ativo
- Via a interface socket, usamos _connect_ para nos conectarmos no lado passivo.
- Enviamos a primeira mensagem com _send_...
- ...e podemos receber respostas com _recv_!
- Eventualmente terminamos nossa conexão e fechamos.