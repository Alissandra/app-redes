## IFRN
## SISTEMAS PARA INTERNET
## Disciplina:  Aplicações de Redes
### Modelo ISO/OSI

Nos anos 1970 a interligação dos primeiros computadores, tanto de uso corporativo como de uso industrial, provocou a criação de soluções proprietárias, ou seja, somente o fabricante tinha o conhecimento da tecnologia envolvida. Dessa forma dificultava e muitas vezes inviabilizava a interconexão de dispositivos de diferentes fabricantes. Para possibilitar a interconexão de dispositivos de fabricantes diferentes.

Em 1978 o Modelo OSI (Open System Interconnection) foi proposto pela ISO (International Standards Organization) e revisado e 1984, dividindo a comunicação em sete camadas para padronizar as redes de computadores e formar um modelo de referência para sistemas que estão abertos à comunicação com outros sistemas. Não é um modelo de arquitetura de rede, pois as camadas não especificam os serviços e protocolos exatos que devem ser usados em cada camada e sim suas funções. 

**Para a criação das sete camadas do Modelo OSI foram seguidos alguns princípios. Segue um resumo dos princípios:**

1.	Se for necessário detalhar uma área;
2.	Cada camada deve executar uma função bem definida;
3.	A função de cada camada deve ser definida tendo em vista os protocolos padronizados mundialmente;
4.	Os limites de camadas devem ser definidos para diminuir o fluxo de informações pelas interfaces;
5.	O número de camadas deve ser grande o bastante para que funções diferentes não precisem ser colocadas na mesma camada e deve também ser pequeno o suficiente para que a arquitetura não se torne difícil de controlar;

**As camadas do Modelo OSI são:**

    1.	Camada Física;
    2.	Camada de Enlace;
    3.	Camada de Rede;
    4.	Camada de Transporte;
    5.	Camada de Sessão;
    6.	Camada de Apresentação;
    7.	Camada de Aplicação;

O bloco específico de informações transferido por uma rede se chama PDU (Protocol Data Unit). O PDU terá diferentes tipos de dados que serão transferido de acordo com cada camada:

1.	Camada física - bruta pedaços (1s ou 0s) transmitidos fisicamente através do Hardware
2.	Camada Data Link - um quadro (ou série de bits)
3.	Camada de rede - um pacote que contém o endereço de origem e destino
4.	Camada de transporte - um segmento que inclui um TCP cabeçalho e datra
5.	Camada de sessão - os dados passados para a conexão de rede
6.	Camada de apresentação - os dados formatados para apresentação
7.	Camada de aplicação - os dados recebidos ou transmitidos por um software aplicação


## As Camadas do Modelo OSI e suas funções:
### 1. Camada Física
Se encarrega da interface mecânica, elétrica e de sincronização, assim como o meio físico de transmissão formada por placas, cabos, antenas, conectores, satélites de comunicação etc.
 
Converte bits que representam “0” e “1” em sinais elétricos/óptico/ondas de rádio para enviar mensagens pelo meio físico e recupera sinais individuais do meio físico para restaurá-los em bits para enviar a mensagem para camada superior de Enlace.

Para enviar com êxito os quadros de bits exige um método de sincronização entre o transmissor e o receptor. Cada bit do quadro representará um sinal. Cada sinal colocado no meio físico tem um determinado tempo para ocupar o meio físico, que é conhecido por tempo de bit. Os sinais são processados pelo dispositivo de recebimento e retornados às suas representações como bits.

Na camada Física do nó de recebimento, os sinais são convertidos em bits novamente. Então os bits são examinados pelos padrões de bit de início e fim do quadro para determinar que um quadro completo foi recebido. A camada Física então envia todos os bits do quadro para a camada de Enlace de Dados.

Os sinais que representam os bits são analisados em tempos específicos de bit para determinar de forma adequada se o sinal representa o “1” ou o “0”. A sincronização é executada com o uso de um clock.

## 2. Camada de Enlace
Transforma um canal de transmissão normal em uma linha que pareça livre de erros de transmissão. Ela mascara os erros reais de modo que a camada de rede não os veja. Nessa camada, não faz diferença se os dispositivos conectados são computadores, switches ou roteadores, todos são vistos como nós.

Para estabelecer uma linha de comunicação confiável, a camada de enlace efetua o controle de erros. O transmissor divide os dados de entrada em quadros de dados e os transmite sequencialmente. Se o serviço for confiável, o receptor confirmará a recepção correta de cada quadro, enviando de volta um quadro de confirmação.

Regula o tráfego, controlando o fluxo de dados evitando que um transmissor rápido sobrecarregue um receptor lento. A camada de Enlace compreende endereço físico, MAC Address – Media Access Control (Controle de acesso a mídia). Recebe os dados em bits e converte em byte, por exemplo, os transformando em unidade de dado, subtraído o endereço físico e encaminha para a camada de rede.

## 3. Camada de Rede
Endereçamento de dispositivos finais – Os dispositivos finais devem ser configurados com um endereço IP exclusivo para identificação na rede.
Encapsulamento – A camada de rede encapsula a unidade de dados de protocolo (PDU) que veio da camada transporte em um pacote. O processo de encapsulamento adiciona informações de cabeçalho IP, como o endereço IP dos hosts de origem (envio) e destino (recebimento).

Roteamento – A camada de rede vai fornecer serviços para direcionar os pacotes a um host de destino em outra rede. Para viajar para outras redes, o pacote deve ser processado por um roteador. A função do roteador é selecionar o melhor caminho e direcionar os pacotes para o host de destino. Um pacote pode cruzar muitos roteadores antes de chegar ao host de destino. Cada roteador que um pacote atravessa para alcançar o host de destino é chamado de salto.

Desencapsulamento – Quando o pacote chega à camada de rede do host de destino, o host verifica o cabeçalho IP do pacote. Se o endereço IP de destino dentro do cabeçalho corresponder ao seu próprio endereço IP, o cabeçalho IP será removido do pacote. Depois que o pacote é desencapsulado pela camada de rede, o PDU resultante é passado para o serviço apropriado na camada de transporte. O processo de desencapsulamento é executado pelo host de destino do pacote IP.

Essa camada também controla os envios e recebimentos para evitar o congestionamento da rede e busca superar problemas para que redes heterogêneas se interconectem. Em rede broadcast o roteamento é simples e as vezes o uso dessa camada é inexistente.

## 4. Camada de Transporte
Responsável pelo serviço de transporte confiável de dados. Sua função básica é aceitar dados da camada acima dela, dividi-los em unidades menores e garantir que todos os fragmentos cheguem corretamente à outra extremidade. As mudanças na tecnologia do hardware devem ser superadas de forma transparente para os usuários, sistemas e aplicações, eliminando assim, a preocupação com as camadas inferiores.
 
Diferente das camadas inferiores que são implementadas em um dos nós, a camada de transporte é implementada nos hospedeiros, mas não nos roteadores, estabelecendo uma comunicação lógica ponta a ponta, ligando origem ao destino. Um programa na máquina de origem mantém uma conversação com um programa semelhante instalado na máquina de destino, utilizando os cabeçalhos de mensagens e mensagens de controle.

Determina o tipo de serviço no momento que a conexão será estabelecida. Serviço que será fornecido à camada de Sessão e aos usuários da rede. Ex.: Rede ponto a ponto, entrega mensagens ou bytes na ordem em que eles foram enviados. 

## 5. Camada de Sessão
Permite que os usuários em diferentes máquinas estabeleçam sessões de comunicação entre eles. Controla o diálogo e quem deve transmitir em cada momento. Gerenciamento de tokens, impedindo que duas partes tentem executar a mesma operação crítica ao mesmo tempo. Sincronização, realizando a verificação periódica de longas transmissões para permitir que elas continuem a partir do ponto em que estavam ao ocorrer uma falha e a subsequente recuperação.

Os protocolos dessa camada são úteis para aplicativos multimídia para os quais é necessário coordenar o tempo de dois ou mais tipos de dados, como voz e imagens em movimento, com alto grau de precisão, como videoconferência e transmissão.

## 6. Camada de Apresentação
Está relacionada à sintaxe e à semântica das informações transmitidas. Provê serviços que permitam que as aplicações de comunicação interpretem o significado dos dados trocados. A camada é responsável por converter os dados de programas e protocolos da camada de aplicação para um formato que possa ser transmitido através da rede e usado por outras aplicações em outros hosts.  

## 7. Camada de Aplicação
Responsável pela interação do usuário com as aplicações, fornecendo para isso uma interface entre os aplicativos e a rede. É a camada mais próxima do usuário final.  A maior parte do tráfego real de dados são gerados a partir desta camada. 

O tráfego pode ser originado ao acessar um site, enviar um e-mail, um comando da telnet, uma requisição de download de arquivo de um FTP etc. É a camada para consumir os dados. Nessa camada são usados os protocolos mais conhecidos como HTTP, FTP e DNS.

As camadas de 1 a 3 são encadeadas. os protocolos são trocados entre cada uma das máquinas e seus vizinhos imediatos e não entre as máquinas de origem e destino, que podem estar separadas por muitos roteadores. As camadas 4 a 7 são de ponta a ponta, onde os protocolos trocados são entre a máquina de origem e destino.

# Referência Bibliográfica
Tanenbaum, Andrew S.; Wetherall, David; Redes de computadores; 5. ed. São Paulo: Pearson Prentice Hall, 2011.
Kurose, James F.; Ross , Keith W.; Redes de computadores e a Internet: uma abordagem top-down/; 6. ed. – São Paulo: Pearson Education do Brasil, 2013.
Network, Dante. CCNA. Características da camada física. Disponível em https://ccna.network/caracteristicas-da-camada-fisica/. Acesso em 13 mai. 2022.
Network, Dante. CCNA. Objetivo da camada de link de dados. Disponível em https://ccna.network/objetivo-da-camada-de-link-de-dados/. Acesso em 13 mai. 2022.
Network, Dante. CCNA. Características da Camada de Rede. Disponível em https://ccna.network/caracteristicas-da-camada-de-rede/. Acesso em 13 mai. 2022.
Network, Dante. CCNA. Aplicação, apresentação e sessão. Disponível em https://ccna.network/aplicacao-apresentacao-sessao/. Acesso em 13 mai. 2022.
Fiodevida. As camadas do modelo OSI. 2021. Disponível em https://fiodevida.com/as-camadas-do-modelo-osi-ilustrado/. Acesso em 14 mai. 2022.
Matheus, Yuri. Alura. Conhecendo o modelo OSI. 2018. Disponível em https://www.alura.com.br/artigos/conhecendo-o-modelo-osi. Acesso em 13 mai. 2022.
Antunes, Fábio. Lecker, Guilherme. Lima, Thaina. Trabalhos da disciplina de Redes de Computadores II. Camada de Enlace. Disponível em https://www.gta.ufrj.br/ensino/eel879/trabalhos_vf_2012_2/80211abg/tipos.html. Acesso em 14 mai. 2022.




