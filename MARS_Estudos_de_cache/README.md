# Material utilizado para exercícios de estudos de cache
- Uso do MARS, IDE para fins didáticos que utiliza arquitetura MIPS.<br>
  - https://courses.missouristate.edu/KenVollmar/MARS/download.htm<br>
- Arquivo tutorial -> Mars_Tutorial.pdf<br>
  - Começa na parte 2, página 4<br>

- Word X Block
    - Palavra é a menor unidade de dados que o processador pode manipular.
      - Word = 8 bytes por exemplo
    - Bloco ou linha de cache é a unidade de dados transferida entre a memória principal e a cache
      
 ![image (2)](https://github.com/user-attachments/assets/8f9f2414-4bcc-4720-8b33-ca18345a3d55)

## Mars_Tutorial.pdf
### row-major.asm
Este programa percorrerá uma matriz de inteiros de 16 por 16 elementos na ordem de varredura por linhas (row-major), atribuindo valores de 0 a 255 aos elementos, em ordem. Ele executa o seguinte algoritmo<br>
![image](https://github.com/user-attachments/assets/229fe55f-c667-4097-b63c-087c5123b523)
- Qual a taxa de acerto(hit rate)?
    - A cada falta, um bloco de 4 palavras é escrito no cache. Em uma varredura em ordem de linha, os elementos da matriz são acessados na mesma ordem em que estão armazenados na memória. Assim, cada falta no cache é seguida por 3 acertos, pois os próximos 3 elementos são encontrados no mesmo bloco de cache. Isso é seguido por outra falta quando o Mapeamento Direto mapeia para o próximo bloco de cache, e o padrão se repete. Portanto, 3 de cada 4 acessos à memória serão resolvidos no cache.<br>
    - Se aumentar o número de blocos não vai mudar a taxa de acerto nesse exemplo, a o tamanho da word vai, sendo a taxa de acerto definida por [(word-1)/word]x100<br>
    - A taxa de acerto para 8 words será 7/8 = 0,75. E a taxa de acerto para 2 words é 1/2 = 0,50 <br>
### column-major.asm
Este programa percorrerá uma matriz de inteiros de 16 por 16 elementos na ordem de varredura por colunas (column-major), atribuindo valores de 0 a 255 aos elementos, em ordem.<br>
![image (1)](https://github.com/user-attachments/assets/3def31a9-7af3-4e7d-92bc-c5985a7180d0)
- Qual a taxa de acerto?
    - O problema é que os endereços de memória agora são acessados não sequencialmente como antes, mas cada acesso está 16 palavras além do anterior (circularmente). Com as configurações que usamos, nenhum dos dois acessos consecutivos à memória ocorre no mesmo bloco, então cada acesso é uma falta
      
    - Como cada acesso é um novo bloco e nenhum bloco é reutilizado, terá 0% taxa de acerto
      ![image (3)](https://github.com/user-attachments/assets/98b7e3a3-c37b-445e-b59b-79a6221253b1)

    - Se a quantidade de blocos for 16 e de word 16, irá errar somente o primeiro acesso aos blocos, depois é só hit rate → (16x16 - 16 )/ 16x16 = 0,9375
  ![image (4)](https://github.com/user-attachments/assets/7cd15fec-d2dd-4268-b630-6fa3e7dd36eb)

