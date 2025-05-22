**História 2 – Relatório Completo sobre**
Foi criado objetivo geral cujo foco é estabelecer diretriz para sprint 2:  
Monitorar bovinos em pasto utilizando sensores IoT de temperatura, umidade e movimento, 
tanto no ambiente quanto nos animais, garantindo bem-estar, prevenção de doenças e melhoria no manejo. 

**Levantamento de Sensores Viáveis**
Antes da divisão em tarefas especificas, foi feito um levantamento inicial com os seguintes critérios: 

1 – Avaliar sensores com baixo custo; 
2 – Avaliar sensores com consumo energético; 
3 – Verificar aplicação ao ambiente (solo, clima); 
4 – Verificar forma de aplicação nos animais (coleira, brinco, embutido); 
5 – outros... 



**Detalhes de Tarefas:** 
**Tarefa 2.1 – Sensores de Temperatura e Umidade para Ambiente**
**Sensores estudados**
**DHT11 / DHT22**
 Sensores amplamente utilizados para medição de temperatura e umidade relativa do ar. Apresentam fácil
 integração com microcontroladores como o ESP32, baixo consumo de energia e bom desempenho em ambientes rurais.
 O DHT22 possui maior precisão e faixa de operação em comparação ao DHT11, sendo mais indicado para 
 monitoramento em abrigos de animais e áreas de pasto.
 ![image](https://github.com/user-attachments/assets/ce60da3f-3f52-4a58-b64a-97478c0165f0)
 ![image](https://github.com/user-attachments/assets/74f74aa8-1763-443a-a74f-36882719de06)

**BME280**
Sensor de alta precisão que combina medição de temperatura, umidade e pressão atmosférica em um único módulo. 
Ideal para aplicações ambientais mais exigentes, o BME280 permite análises mais completas do microclima local,
contribuindo para decisões mais assertivas no manejo de animais e instalações.
 ![image](https://github.com/user-attachments/assets/14394055-0444-4124-b3dc-eea2e19e2780)
 ![image](https://github.com/user-attachments/assets/2d655af1-9d30-458a-a885-d4907956fd11)


**Resultados**
 Tanto o DHT22 quanto o BME280 demonstraram-se viáveis para uso em ambientes externos, desde que protegidos
adequadamente contra intempéries (chuva, poeira e sol direto) por meio de caixas com proteção IP (Ingress Protection).
Segudo os artigos encontrados na pesquisa, ambos os sensores apresentaram estabilidade nas leituras
e boa resposta às variações ambientais, com destaque para a maior precisão e recursos adicionais do BME280.
 


**Tarefa 2.2 – Sensores de Temperatura Corporal e Movimento para Animais**
**Sensores de temperatura corporal**
**MLX90614 (Infravermelho sem contato)**
Ideal para medições de temperatura sem necessidade de contato físico, o MLX90614 é útil em situações
em que o estresse ou o manuseio do animal deve ser minimizado. Pode ser posicionado em pontos estratégicos
próximos ao corpo do animal, como em estruturas de passagem ou bebedouros.
  ![image](https://github.com/user-attachments/assets/0fc73dc6-7f5e-4ff0-8c00-945c3e007dc9)
 
**DS18B20 (Contato direto)**
Utilizado em contato direto com o animal, como inserido em coleiras, o DS18B20 fornece leituras precisas 
da temperatura corporal. Sua instalação é simples e seu baixo custo o torna uma opção viável para monitoramento
contínuo em campo.
  ![image](https://github.com/user-attachments/assets/9bcd8ecb-beec-4609-9097-a5175d437029)

**Sensores de movimento**
**MPU6050 (Acelerômetro + Giroscópio)**
Este sensor combina dados de aceleração e rotação, permitindo detectar padrões de movimento, inclinação, 
quedas e períodos de inatividade. Seu uso em coleiras se mostrou altamente eficaz para monitoramento
comportamental de animais de forma não invasiva.
  ![image](https://github.com/user-attachments/assets/1747a3d7-e215-4114-98cc-1d0b1cf4ecc6)
  ![image](https://github.com/user-attachments/assets/4898a09a-f4cf-4a8d-97a3-0100a6437741)

**Resultados**
O sensor MPU6050 embutido em coleiras demonstrou ser promissor para a detecção de movimentação,
repouso e possíveis quedas dos animais. 
Além disso, os sensores MLX90614 e DS18B20 forneceram medições consistentes de temperatura. 
O MLX90614, por ser sem contato, é ideal para ambientes controlados ou para uso em pontos de passagem. 
Já o DS18B20, quando acoplado às coleiras, mostra - se precisão e estabilidade nas leituras, sendo mais 
apropriado para monitoramento contínuo e individualizado.

**Tarefa 2.3 – Levantamento de Sensores de Solo e GPS**
**Sensores estudados**
**FC-28 (Sensor de Umidade do Solo)**
Sensor analógico e digital que mede o nível de umidade do solo, útil para avaliar as condições de
pastagens e auxiliar no manejo de irrigação ou movimentação do rebanho. Fácil integração com
microcontroladores e baixo custo.

**Sensor Capacitivo de Umidade do Solo (v1.2)**
Utiliza variação capacitiva para medir a umidade, sem contato direto com o solo, o que o torna mais
resistente à corrosão. Apresenta maior durabilidade e é indicado para monitoramento contínuo em campo aberto.

**SHT20 com Sonda Impermeável (Umidade e Temperatura do Solo)**
Sensor digital de alta precisão, mede simultaneamente a umidade volumétrica e a temperatura do solo.
A sonda selada é resistente à água, ideal para uso prolongado em ambientes externos. Comunicação via I2C,
com excelente compatibilidade com o ESP32. Indicado para aplicações que exigem dados confiáveis para rodízio 
de pastagem, monitoramento térmico do solo e mapeamento agroambiental.

**NEO-6M GPS Module**
Módulo GPS de baixo custo com boa sensibilidade e cobertura em áreas abertas, ideal para rastreamento
de animais em campo. Permite identificar a localização geográfica com precisão razoável e pode ser
utilizado em conjunto com sensores de movimento e temperatura.

**Resultados**
Os sensores FC-28, sensor capacitivo de umidade, e SHT20 com sonda impermeável foram considerados adequados para 
monitoramento de solo em ambientes rurais. O SHT20 se destaca por sua alta precisão e resistência a condições
climáticas adversas, sendo o mais indicado para aplicações de longo prazo. Já o NEO-6M apresenta boa recepção de 
sinal e compatibilidade com o ESP32, tornando-se uma solução viável para localização e rastreamento de animais em pasto aberto.

**Tarefa 2.4 – Verificação de Compatibilidade com Microcontroladores (ESP32)**
**Microcontrolador escolhido**
**ESP32**
Microcontrolador com conectividade Wi-Fi e Bluetooth, ideal para projetos IoT. Possui múltiplas interfaces de 
comunicação (I2C, SPI, UART), bom poder de processamento e ampla comunidade de suporte.
Possui a comunicação via I2C, SPI e UART com os sensores:
MLX90614
DS18B20
DHT22 / BME280
MPU6050
FC-28
NEO-6M
Entre outros..

**Resultados**
Todos os sensores listados já foram reconhecidos corretamente pelo ESP32, com bibliotecas estáveis disponíveis no Arduino IDE.
A comunicação via I2C, SPI e UART foi bem-sucedida em testes práticos, comprovando a viabilidade técnica de integração em 
um sistema embarcado para monitoramento ambiental e animal.

**Tarefa 2.5 – Consumo Energético e Viabilidade em Campo**
Critérios analisados: 
Consumo em mA de cada sensor e do ESP32. 
Modos de deep sleep do ESP32 para economia. 
Uso de baterias Li-Ion (18650) e pequenos painéis solares. 

**Resultados:** 
Sistema pode funcionar com autonomia de até 3–5 dias com bateria recarregável e painel solar auxiliar. 

**Tarefa 2.6 – Sensores de Batimento Cardíaco**
Sensores estudados: 
Pulse Sensor (com contato): uso limitado pela dificuldade de posicionamento em animais. 
MAX30100 / MAX30102: Oxímetro e frequência cardíaca por infravermelho. 

Resultados: 
MAX30102 viável com adaptação em brinco ou coleira com contato com pele fina (ex: orelha). 

 Conclusão Geral 
Todos os sensores levantados podem ser conectados ao ESP32. 
Sistema modular pode ser implementado com sensores no ambiente (solo, clima) e sensores no animal (coleira/brinco). 
A infraestrutura IoT está pronta para ser testada em protótipo com foco em: 
Monitoramento ambiental 
Monitoramento de comportamento animal 
Coleta e transmissão de dados para um servidor central

[Estudo de Viabilidade técnica.docx](https://github.com/user-attachments/files/20394354/Estudo.de.Viabilidade.tecnica.docx)


Referencias 

1 - https://agris.fao.org/search/en/providers/122439/records/64747252425ec3c088f2a353 
2 - https://www.makerhero.com/produto/sensor-de-umidade-e-temperatura-dht11/?srsltid=AfmBOop5ti_thrZ02JSh4TGa6Na9-XqZHtPUs3UxPLO8u2qdbU5jLhBB 
3 - https://www.robocore.net/sensor-robo/acelerometro-e-giroscopio-mpu6050?srsltid=AfmBOopCUZKjfOwOHgHua2cdnzGps0vEyBoBsTHueBz-fGqluIJ2EZar 
4 - https://www.alldatasheet.com/datasheet-pdf/view/224153/MELEXIS/MLX90614.html 
5 - https://www.eletrogate.com/modulo-gps-neo-6m-com-antena?srsltid=AfmBOoqqI4xFoS7y4eX--9nXfxQzDKu5xq4YhqI1zFSLlQgiVoKJraaz 
6 - https://s3.amazonaws.com/westgen/wp-content/uploads/2017/06/19140218/HT-Pro_16_A4_Eng_Nov15_low.pdf 
7 - https://www.cowmanager.com/cow-management/ 
8 - Sensor de temperatura e umidade DHT22 (AM2302) - Arduino e Cia 
9 - DS18B20 - Sensor de temperatura inteligente com Arduino | Portal VDS 
10 - DS18B20 pdf, DS18B20 Descrição, DS18B20 Folha de dados, DS18B20 view ::: ALLDATASHEET ::: 
11 - Sensor BME280 para Pressão, Umidade e Temperatura - Blog UsinaInfo 
12 - BME280 pdf, BME280 Descrição, BME280 Ficha técnica, BME280 view ::: ALLDATASHEET ::: 
