# Material utilizado para exercícios de estudos de cache
- Uso do MARS, IDE para fins didáticos que utiliza arquitetura MIPS.<br>
  - https://courses.missouristate.edu/KenVollmar/MARS/download.htm<br>
- Arquivo tutorial -> Mars_Tutorial.pdf<br>
  - Começa na parte 2, página 4<br>

- Word X Block
    - Palavra é a menor unidade de dados que o processador pode manipular.
      - Word = 8 bytes por exemplo
    - Bloco ou linha de cache é a unidade de dados transferida entre a memória principal e a cache
## Mars_Tutorial.pdf
### row-major.asm
Este programa percorrerá uma matriz de inteiros de 16 por 16 elementos na ordem de varredura por linhas (row-major), atribuindo valores de 0 a 255 aos elementos, em ordem. Ele executa o seguinte algoritmo<br>
![image](https://github.com/user-attachments/assets/229fe55f-c667-4097-b63c-087c5123b523)
- Qual a taxa de acerto(hit rate)?
    - A cada falta, um bloco de 4 palavras é escrito no cache. Em uma varredura em ordem de linha, os elementos da matriz são acessados na mesma ordem em que estão armazenados na memória. Assim, cada falta no cache é seguida por 3 acertos, pois os próximos 3 elementos são encontrados no mesmo bloco de cache. Isso é seguido por outra falta quando o Mapeamento Direto mapeia para o próximo bloco de cache, e o padrão se repete. Portanto, 3 de cada 4 acessos à memória serão resolvidos no cache.<br>
    - Se aumentar o número de blocos não vai mudar a taxa de acerto nesse exemplo, a o tamanho da word vai, sendo a taxa de acerto definida por [(word-1)/word]*100<br>
