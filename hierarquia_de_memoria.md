# Hierarquia de Memória
- Livro "Organização e Projeto de Computadores" (Página 614 - 807)<br>
## Conceitos
- Hierarquia de memória consiste em múltiplos níveis de memória com diferentes velocidades e tamanhos<br>
- Conforme a distância da memória em relação ao processador aumenta, o tamanho e o tempo de acesso aumenta<br>
- nível superior(próximo do processador) vs nível inferior(distante do processador) <br>
- As memórias mais rápidas são mais caras e menores por bit do que as memórias mais lentas e maiores<br>

![image](https://github.com/user-attachments/assets/5d3a3d27-5d3f-45c4-a843-538477d853e2)


### Localidade Temporal
- Se um local de dados é referenciado, então ele tenderá a ser referenciado de novo em um curto espaço de tempo<br>
### Localidade Espacial
- Se um local de dados é referenciado, então os dados com endereços próximos possivelmente serão acessados futuramente<br>
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


