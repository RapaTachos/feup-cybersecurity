# Trabalho realizado na Semana #4


## Tarefa 2.1
- Quando um programa é executado,recebe informações do ambiente no qual está a ser executado. Essas informações de ambiente são passadas implicitamente via variáveis de ambiente. Esses valores são, por exemplo, a localização do sistema, tipo do terminal, etc.
- Todos os valores das variáveis de ambiente são strings não nulas.


## Tarefa 2.2
- **Passo 1:** Depois de compilar e executar, gravamos o output em file1 que recebe as variáveis ambiente do processo filho.
- **Passo 2:** Depois de compilar e executar, gravamos o output em file2 que recebe as variáveis ambiente do processo pai.  
- **Passo 3:** Correndo o comando "**diff file1 file2**" conseguimos reparar que não existem diferenças entre os ficheiros.
- Concluímos que o processo filho herda as variáveis de ambiente do processo pai.

## Tarefa 2.3
- No 1º passo não obtivemos qualquer output.
- Alterando a invocação do execve() para " **execve("/usr/bin/env", argv, environ);** ", ja obtemos output.
- Esta função **execve ()** substitui a imagem do processo atual por uma nova imagem do processo especificada por **argv."/usr/bin/env"**, mostra-nos então o caminho para o novo arquivo de imagem do processo. **Argv** indica-nos a lista de strings disponível para a nova imagem do processo, deve ser assegurado que o último membro de argv aponte para NULL.**Environ** é um array de apontadores , que apontam para as strings da nova imagem do processo. São assim imprimidas as variáveis ambiente em **"/usr/bin/env"**.

## Tarefa 2.4
- O comando é executado e obtemos as variáveis de ambiente.

## Tarefa 2.5 
- Apenas conseguimos exportar a 3ª variavel no passo 3.
- Depois de compilar, trocar permissões e criar uma variável de ambiente personalizada.
- Correndo o comando | diff file1 file2_5 |   obtivemos a variavel criada (banana_var_teste).
``` 
> MYVAR=banana_var_teste
49c50
< _=./a.out
---
> _=./printUID.out
```

## Tarefa 2.6
- Correndo o comando 'whoami' dentro da chamada  a 'system()' no programa continuamos como seed.
- No entanto conseguimos correr '**sudo -i**'  e abrir uma shell como root e conseguímos **'chmod's** então facilmente poderiamos realizar alterações.



