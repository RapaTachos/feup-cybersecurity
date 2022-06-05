# CTF Semana #10

## Desafio 1

- Começando a explorar o desafio ele aparenta logo algumas semelhanças com ctf da google 'Pasteurize'. Tentamos entao inserir um bloco de HTML para ver como o servidor poderia reagir.

![Figura 10_1](pic10_1.png)

- De facto a tag h1 foi incorporada, o que mais tarde nos levou a tentar scripts.
- Notámos tambem que havia um form que fazia post para obter a flag, no entanto o input estava 'disabled'. Tentamos alterar este valor manualmente mas não funcionava. Para além disso a página executa um script que a cada 5 segundos faz reload da página.

![Figura 10_2](pic10_2.png)

- De seguida tentamos então passar um bloco **script** apenas com a instrução de **window.alert** e o alert foi executado.

![Figura 10_3](pic10_3.png)

![Figura 10_4](pic10_4.png)

- Restava apenas juntar todas estas peças. Como sabemos o id do botão conseguimos obte-lo com **document.getElementById** e forçar um **click()** para obter a flag.

![Figura 10_5](pic10_5.png)

```html
<script>document.getElementById('giveflag').click();</script>
```


