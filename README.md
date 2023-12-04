# Arduino-automacao-de-ar-condicionado

Passo a passo.
http://www.instructables.com/id/Ar-Condicionado-controlado-por-Arduino-via-infrave/

Projeto Automação ar condicionado via Infravermelho(IR) e Arduino.

Mais detalhado em: Tutorial na Medium

Neste tutorial ensinarei como acionar um ar condicionado a partir de um Arduino MEGA, de acordo com a temperatura medida em um sensor LM35. 
Veremos também o famoso “pulo do gato” na hora de receber um sinal IR de um controle de ar condicionado, pois é um sinal muito comprido e 
não é qualquer código que consegue ler este por completo, gerando uma grande dor de cabeça aos iniciantes.

Daí você poderá usar sua imaginação para utilizar esse aprendizado! Mão na massa!

Precisaremos de:

    Um Arduino MEGA ou UNO; No exemplo utilizarei o MEGA;
    Um sensor LM35;
    Um sensor IRM-3638 (Leitor de Infravermelho);
    Um LED IR (Emissor Infravermelho);
    Um resistor de 10 Ω;
    Fios;
    Equipamentos para solda dos componentes;
    Códigos que disponibilizarei;

Primeiro ligaremos o Arduino MEGA de forma que teremos três circuitos, um para LER o sinal IR (o como IRM-3638), outro para ENVIAR com o LED IR 
e ainda um terceiro para LER a temperatura. Lembrando que ora carregaremos o código de leitura de IR e ora carregaremos o código de envio de IR e
monitoração de temperatura, segue o esquema nas imagens acima:

Na figura acima já coloquei a ligação dos componentes, porém, é sempre importante da uma verificada na DATASHEET do componente, para saber onde 
ligar certo, ao final do post colocarei o link para as respectivas datasheets!

Carregaremos a bilbioteca IRremote disponível nesse link: http://www.righto.com/2009/08/multi-protocol-infr... , 
removendo a atual do Arduino, veja o link para maiores detalhes.

Com nosso Arduino MEGA conectado aos respectivos circuitos, carregaremos o seguinte código:

http://www.analysir.com/blog/wp-content/uploads/20...

(Veja mais sobre o porquê desse código e não de outros códigos de leitura de ID:

http://www.analysir.com/blog/2014/03/19/air-condit...

Carrega o código, ainda na interface padrão do Arduino abriremos em FERRAMENTAS>> MONITOR SERIAL(ou CTRL + ALT + M), quando este abrir não se esqueça 
de mudar o BAUD RATE para 115200, o mesmo do código, feito isso você pode aperta o botão cuja função deseja copiar para que posteriormente seja repetida,
veja nas imagem acima

Esse código acima marcado é o sinal RAW referente a função apertada no controle remoto. Copie esta e retire todos os sinais negativos desta sequência,
para podermos envia-los pelos código, você deve estar se perguntando, putz mais são muitos negativos para retirar, calma guerreio, fiz um programa 
em Java que vai te ajudar a padronizar esse sinal, segue nas images acima e link para download:

Download: https://drive.google.com/file/d/0B7Bje74bGvcBYnVWY...

De posse do código RAW, já padronizado, abriremos a interface de desenvolvimento do Arduino novamente e colaremos o código abaixo, esse código é 
responsável por Enviar o sinal IR em formato RAW de acordo com a leitura de uma determinada TEMPERATURA, o código está todo comentado, só o olhar 
o local de colar o código RAW para o Arduino e ver os resultados. Depois é só utilizar a imaginação e aplicar do jeito que você achar melhor!

Att.

Deividson Calixto da Silva.
