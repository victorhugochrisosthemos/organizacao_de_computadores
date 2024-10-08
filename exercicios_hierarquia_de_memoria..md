# 1. Calculando o número total de bits de uma cache diretamente mapeada
- Exercício da página 645 do livro Organização e Projeto de Computadores<br>
## Dados iniciais
- 16 KiB de dados<br>
- Blocos de 4 palavras<br>
- Endereçamento de 32 bits<br>
## Notações importantes
- 1 KiB = Kibibyte = 2^10 bytes<br>
- 1 byte = 8 bits<br>
- 1 Kb = Kilobit = 1000 bits<br><br><br>
![image](https://github.com/user-attachments/assets/e3b2b33d-3c32-4d5b-b56a-f1fa4a6f6c9a)


## Calculando o tamanho do bloco / offset / deslocamento
- Cada palavra tem 4 bytes<br>
- 4 palavras X 4 bytes = 16 bytes<br>
- Log2(16) = 4 bits de tamanho do bloco<br>
## Número de blocos / Linhas da cache / Quantidade de índices
- Quantidade de dados / Tamanho do bloco<br>
- O total de blocos terá que comportar a quantidade de dados<br>
- Quantidade de dados = 16 KiB<br>
- 16 KiB = 16 x 2^10 = 16 x 1024 = 16384 bytes<br>
- 16384 bytes / 16 bytes = 1024 blocos<br>
- Log2(1024) = 10 bits de índice<br>
## Número de bits da tag
- É o que sobrar de bits do endereçamento<br>
- Endereçamento - Offset - Índice = Tag<br>
- 32 - 4 - 10 = 18 bits de tag<br>
## Calculando o número total de bits
- Dados de armazenamento<br>
  - 16 KiB = 16 x 2^10 = 16 x 1024 = 16384 bytes = 16384 x 8 = 131072 bits<br>
- bits de tag por linha<br>
  - 18 bits x 1024 linhas = 18432 bits<br>
- bit de validade<br>
  - 1 x 1024 linhas = 1024 bits<br>
- Somando tudo<br>
  -> 131072 x 18432 x 1024 = 150528 bits<br>

#### Outra forma de calcular o tamanho da cache é calcular 1 endereçamento e multiplicar pela quantidade de blocos/linhas/índice

# 2. Mapeando um endereço para um bloco de cache multipalavra
## Considerações iniciais
- Cache com 64 blocos<br>
- 16 bytes por bloco<br>
- Qual o número do bloco/índice do endereço 1200 bytes mapeado?
## Notações importantes
-  O módulo na matemática é o resto de uma divisão<br><br><br>
![image](https://github.com/user-attachments/assets/800793cc-f557-4904-9775-0c8c16aa5457)

## Endereço do bloco
- (Endereço do bloco) módulo (Número de blocos de cache)<br>
- 1200 / 16 = 75<br>
- Com isso, o endereço 1200 está no bloco 75 da memória principal<br>
## Determinar o número do bloco na cache<br>
- A cache tem 64 blocos<br>
- 75 mod 64 = 11<br>
- Finalizando, o endereço 1200 está no bloco 11 da memória da cache<br>

# 3. Possíveis questões para a prova, não tenho certeza...
#### 3.1. Como calcular o tamanho da cache?
#### 3.2. O que é e como calcular o overhead na cache?
- Overhead refere-se à quantidade de dados adicionais que são necessários para gerenciar a cache além dos dados reais que estão sendo armazenados
- Pode ser calculado o overhead <br>
  -> bits de controle X número de blocos <br>
  -> bits de controle podem ser tag, bit de validade, etc <br>
  -> porcentagem de overhead -> (bits de controle / tamanho da cache) X 100 <br>
#### 3.3. Descreva as características gerais de um programa
- Localidade temporal e espacial no acesso a dados:
  - Alta localidade temporal: Acessa suas variáveis várias vezes em um curto intervalo de tempo.
  - Baixa localidade temporal: Acessa suas variáveis uma única vez ou raramente (taxa de acertos no cache baixa).
  - Alta localidade espacial: Realiza acessos sequenciais a posições de memória adjacentes, como em vetores.
  - Baixa localidade espacial: Acessa posições de memória distantes entre si, de forma não sequencial (pouco uso da função dos blocos na cache).

- Localidade temporal e espacial no acesso a instruções:
  - Alta localidade temporal: As instruções são executadas repetidamente, como em loops ou chamadas frequentes a funções.
  - Baixa localidade temporal: As instruções são executadas uma única vez ou com pouca frequência.
  - Alta localidade espacial: As instruções próximas na memória são executadas em sequência, como em blocos de código ou funções lineares.
  - Baixa localidade espacial: As instruções estão espalhadas por diferentes locais na memória e são acessadas de forma não sequencial.
#### 3.4. Falhas de cache
#### 3.5. write-through
#### 3.6. buffer de escrita
#### 3.7. write-back
#### 3.8. TMAM
![image](https://github.com/user-attachments/assets/dabdcc5f-618f-4c08-99f9-16d31ffe081f)
