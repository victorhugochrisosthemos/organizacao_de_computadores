# 1.Calculando o número total de bits de uma cache diretamente mapeada
- Exercício da página 645 do livro Organização e Projeto de Computadores<br>
## Dados iniciais
- 16 KiB de dados<br>
- Blocos de 4 palavras<br>
- Endereçamento de 32 bits<br>
## Notações importantes
- 1 KiB = Kibibyte = 2^10 bytes<br>
- 1 byte = 8 bits<br>
- 1 Kb = Kilobit = 1000 bits<br>
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

# 2.Mapeando um endereço para um bloco de cache multipalavra
## Considerações iniciais
- Cache com 64 blocos<br>
- 16 bytes por bloco<br>
- Qual o número do bloco-ínndice o endereço em bytes 1200 é mapeado?
## Notações importantes
-  O módulo na matemática é o resto de uma divisão<br>
![image](https://github.com/user-attachments/assets/800793cc-f557-4904-9775-0c8c16aa5457)

## Determinar o deslocamento / offset / tamanho do bloco
- Cada bloco tem 16 bytes -> log2(16) = 4 bits para o offset
## Endereço do bloco
- (Endereço do bloco) módulo (Número de blocos de cache)<br>
- 1200 mod 16 = 75<br>
- Com isso, o endereço 1200 está no bloco 75 da memória pincipal<br>
## Determinar o número do bloco na cache<br>
- A cache tem 64 blocos<br>
- 75 mod 64 = 11<br>
- Finalizando, o endereço 1200 está no bloco 11 da memória da cache<br>
