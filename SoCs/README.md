# System on Chip (SoC)
A transformação tecnológica em que estamos vivendo exige grande capacidade de processamento, 
com um alto desempenho para sustentar as mudanças de paradigmas propostos pela inteligência 
artificial e a IoT (internet das coisas), por exemplo.<br>

A fim de melhorar o desempenho nesse cenário, a tecnologia SoC (System-On-Chip) ganha espaço 
gerando circuitos integrados com processadores, memórias, interfaces e controladores licenciados 
por diferentes empresas. Com blocos de IP (Intellectual Property) na criação de SoCs, uma empresa 
pode desenvolver um design personalizados para a solução de seus problemas.<br>

Intel, ARM, AMD, Apple e NVIDIA são umas das empresas que estão utilizando arquitetura SoCs em 
seus produtos. Nesse contexto, é importante entendermos mais sobre como funciona essa tecnologia. 
Dito isso, a sua evolução está diretamente ligada ao VLSI (Very Large Scale Integration), um 
tecnologia de microeletrônica capaz de integrar bilhões de transistores em um pequeno espaço, 
melhorando o desempenho e o custo energético (quanto menor a área, menos calor dissipado). 
Parte desse desenvolvimento foi impulsionada pela constatação da Lei de Moore, indicando 
um aumento exponencial de transistores a cada dois anos nos circuitos integrados.<br>

Dentro desses sistemas em chips, você pode se deparar com processadores integrados que 
podem ser de arquitetura CISC (Complex Instruction Set Computing) ou 
RISC (Reduced Instruction Set Computing). O CISC está relacionado com maior 
complexidade nas instruções processadas, encontramos essa arquitetura mais em PCs 
desktop ou em servidores. Já o RISC preza por um núcleo de instruções mais reduzidos 
para melhorar o desempenho com a rapidez gerada na execução de menor número de ciclos 
por instruções, a qual podemos encontrar em smartphones e dispositivos IoT. Sobre 
essas questões de arquiteturas, uma que também vale comentar é a RISC-V.<br>

No cenário de SoCs, dispositivos que funcionam com RISC-V são importantes 
porque permitem maior customização, contribuindo para a customização de um 
circuito de diferentes blocos IP. Além disso, o RISC-V possui outros benefícios 
devido a ser de código aberto (diminui os royalties à pagar), trabalhar com uma 
estrutura de pipeline e a possibilidade de aplicar soluções com computação 
paralela (utilizados para minimizar o tempo de execução de instruções por clock). 
Ainda sobre customização, nos circuitos desses chips, o protocolo mais utilizado 
para a interconexão dos diferentes componentes é o 
AMBA (Advanced Microcontroller Bus Architecture), um padrão de comunicação 
no ecossistema SoC que permite interoperabilidade e escalabilidade com 
eficiência.<br>

Na fase de desenvolvimento, o  uso de FPGA (field-programmable gate array) 
auxilia na criação de um protótipo para validar o correto funcionamento 
de uma arquitetura antes de criar um SoC. Um FPGA é um circuito integrado 
programável, onde possui portas lógicas, inputs, outputs e memória que pode 
ser programado via VHDL para representar uma solução de hardware. Depois de
feito testes e validado, já é possível criar um ASIC, um circuito integrado 
criado para a solução de um problema específico como mineração de criptomoedas. 
Porém, diferente do SoC, o ASIC é altamente personalizado, e o SoC possui o foco 
em ser um sistema computacional em um único chip com flexibilidade de integração.<br>
