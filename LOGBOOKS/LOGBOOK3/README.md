# Trabalho realizado na Semana #3

## Identificação

- Apos deliberar varias alternativas escolhemos o CVE-2021-37538.
- Esta vulnerabilidade trata-se de uma injeção de SQL   
 no módulo **SmartBlog Prestashop** da **SmartDataSoft**.


## Catalogação

- O ataque foi descoberto a 22/06/2021 durante um teste de intrusão através da injeção de código sql malicioso.
- Foi atribuído um nível de gravidade de 7.5 onde o impacto da confidencialidade, integridade e disponibilidade foram considerados parciais,no entanto a complexidade do acesso foi considerada baixa sendo necessário pouco nível de experiência e conhecimento para executar o exploit.
- A autenticação no site não era necessária para explorar esta vulnerabilidade.   

## Exploit

- Durante o processo de registo era pedido ao utilizador a sua data de nascimento que era passada para uma query não sanitizada como string em vez de um inteiro (1-12, que já não seria passível de injeção).
- É possivel dar escape usando um comentário no final da query ( -- ) de maneira a não crashar o código e obter algo de volta. 
- Em **controllers/front/archive.php**  conseguimos ver os parametros do dia, mes e ano que são passados à funçao **getArchiveResult()** sem sanitização.
- item4

## Ataques

- Reportado à empresa dia 13/07/2021, resolvido dia 15/07/2021.
- Aos valores que precisavam de ser sanitizados podia ser dado cast para inteiros então o problema foi rapidamente abordado pela SmartDataSoft após tomarem conhecimento do CVE.
- Por isso não aparenta haver registo de  ataques.
- item4

---

## Falta:

- Prestashop pSQL
pSQL() is intended for string escaping



- em 'National Vulnerability Database' encontrei, **Weakness Enumeration:**  
    > CWE-89 -> Improper Neutralization of Special Elements used in an SQL Command ('SQL Injection')


- revisão geral do texto -> procurar erros, acertar texto, apagar items não usados, verificar se todos os paragrafos fazem sentido entre si  (como escrevemos partes diferentes)
