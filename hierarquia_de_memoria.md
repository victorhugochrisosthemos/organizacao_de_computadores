# Hierarquia de Memória
- Livro "Organização e Projeto de Computadores" (Página 614 - 807)<br>
## Conceitos
- Hierarquia de memória consiste em múltiplos níveis de memória com diferentes velocidades e tamanhos<br>
- Conforme a distância da memória em relação ao processador aumenta, o tamanho e o tempo de acesso aumenta<br>
- Nível superior(próximo do processador) vs Nível inferior(distante do processador) <br>
- As memórias mais rápidas são mais caras e menores por bit do que as memórias mais lentas e maiores<br>

![image](https://github.com/user-attachments/assets/5d3a3d27-5d3f-45c4-a843-538477d853e2)


### Localidade Temporal
- Se um local de dados é referenciado, então ele tenderá a ser referenciado de novo em um curto espaço de tempo<br>
- Mantêm dados mais acessados recentemente do processador<br>
### Localidade Espacial
- Se um local de dados é referenciado, então os dados com endereços próximos possivelmente serão acessados futuramente<br>
- Move blocos de múltiplas palavras próximas na memória para níves superiores na hierarquia<br>
### Bloco/Linha
- Unidade mínima de informação que pode estar presente ou não em uma cache<br>
### Taxa de acertos
- A proporção de acessos à memória encontrados no nível superior<br>
- Conceito usado como medida do desempenho da hierarquia da memória<br>
### Taxa de erros
- Taxa de falhas = 1 - Taxa de acertos<br>
- É a proporçao de acessos à memória não encontrados em um nível da memória<br>
### Tempo de acerto
- O tempo necessário para acessar um nível da hierarquia de memória, incluindo se o acesso é um acerto ou falha.<br>
### Penalidade de Falha
- O tempo na busca de um bloco de nível inferior para um nível superior, incluindo o tempo para acessar o bloco, transmiti-lo de um nível a outro e inseri-lo no nível que experimentou a falha, e depois passar o bloco a quem o solicitou.<br>
### --------------------------------------------------------------------------------------------

![image](https://github.com/user-attachments/assets/0d890c9e-cac1-4754-9dfd-777aa1ea3573)

- Se a taxa de acertos for
bastante alta, a hierarquia de memória terá um tempo de acesso efetivo,
próximo ao tempo de acesso do nível mais alto (e mais rápido) e um tamanho
igual ao do nível mais baixo (e maior).<br>
- Afirmações:<br>
  - As hierarquias de memória tiram proveito da localidade temporal.<br>
  - Em uma leitura, o valor retornado depende de quais blocos estão na cache.<br>
  - A maioria do custo da hierarquia de memória está no nível mais alto.<br>
  - A maioria da capacidade da hierarquia de memória está no nível mais baixo.<br>
- O custo das memórias aumenta conforme a frabricação aumenta a área por bit de memória<br>
![image](https://github.com/user-attachments/assets/43fa518d-c54c-409a-b66e-208b86986d6b)

### Tecnologias de Memória
#### SRAM
#### DRAM
#### Memória Flash
#### Memória em Disco
### Princípios Básicos de Cache
- Cache
  - Um lugar seguro para guardar ou esconder coisas.<br>
  - Termo usado para referenciar qualquer armazenamento usado
para tirar proveito da localidade de acesso.<br>
- Como sabemos se um dado está na cache?
#### Cache de Mapeamento Direto
- Uma estrutura de cache em que cada local de memória é mapeado exatamente para um local na cache<br>
- Mapeamento para localizar um bloco -> (Endereço de bloco)módulo(Nº blocos na cache)<br>

![image](https://github.com/user-attachments/assets/b3af53fe-8e23-456c-ae90-522d9c5a64a1)


