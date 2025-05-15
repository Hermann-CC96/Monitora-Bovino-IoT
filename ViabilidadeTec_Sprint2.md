**História 2 – Relatório Completo sobre**
Foi criado objetivo geral cujo foco é estabelecer diretriz para sprint 2:  
Monitorar bovinos em pasto utilizando sensores IoT de temperatura, umidade e movimento, tanto no ambiente quanto nos animais, garantindo bem-estar, prevenção de doenças e melhoria no manejo. 

**Levantamento de Sensores Viáveis**
Antes da divisão em tarefas especificas, foi feito um levantamento inicial com os seguintes critérios: 

1 – Avaliar sensores com baixo custo; 
2 – Avaliar sensores com consumo energético; 
3 – Verificar aplicação ao ambiente (solo, clima); 
4 – Verificar forma de aplicação nos animais (coleira, brinco, embutido); 
5 – outros... 

 

**Detalhes de Tarefas:** 
Tarefa 2.1 – Sensores de Temperatura e Umidade para Ambiente 
Sensores estudados: 
  DHT11 / DHT22: Boa precisão, fácil integração com ESP32, ideal para medir temperatura e umidade em abrigos e pastos. 
  BME280: Alta precisão, sensor combinado de temperatura, umidade e pressão. 

Resultados: 
  DHT22 e BME280 foram considerados viáveis para uso externo, com proteção IP para intempéries. 

Tarefa 2.2 – Sensores de Temperatura Corporal e Movimento para Animais 
Sensores de temperatura corporal:
  MLX90614 (Infravermelho sem contato) para medição sem invasão. 
  DS18B20 (Contato direto) para inserção em coleiras. 
Sensores de movimento: 
  MPU6050 (Acelerômetro + giroscópio): Detecta comportamento, queda, e movimento dos animais. 

Resultados: 
MPU6050 embutido em coleira mostrou-se promissor para detecção de movimentação e inatividade. Sendo que 

Tarefa 2.3 – Levantamento de Sensores de Solo e GPS 
Sensores de solo: 
FC-28: Mede umidade do solo, ideal para entender a condição do pasto. 
GPS: 
NEO-6M GPS Module: Baixo custo, boa cobertura em área aberta. 

Resultados: 
FC-28 e NEO-6M foram considerados adequados para uso em campo aberto, com bom suporte pelo ESP32. 

Tarefa 2.4 – Verificação de Compatibilidade com Microcontroladores (ESP32) 
Microcontrolador escolhido: ESP32 (Wi-Fi + Bluetooth) 
Testes feitos: 
Bibliotecas e comunicação I2C/SPI/UART com os sensores listados. 

Resultados: 
Todos os sensores testados são compatíveis e têm bibliotecas disponíveis no Arduino IDE para ESP32. 

Tarefa 2.5 – Consumo Energético e Viabilidade em Campo 
Critérios analisados: 
Consumo em mA de cada sensor e do ESP32. 
Modos de deep sleep do ESP32 para economia. 
Uso de baterias Li-Ion (18650) e pequenos painéis solares. 

Resultados: 
Sistema pode funcionar com autonomia de até 3–5 dias com bateria recarregável e painel solar auxiliar. 

Tarefa 2.6 – Sensores de Batimento Cardíaco 
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
