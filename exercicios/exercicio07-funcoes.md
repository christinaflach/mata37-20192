# Funções


1. Considere o programa em C que lê um real x e um inteiro n > 0 e calcula x _elevado_ a n. 
Reescreva o programa, usando uma função chamada "potencia" para calcular  x _elevado_ a n, 
e chamando a função "potencia" no corpo de "main". Coloque no repl.it.

Obs.: Esse exercício foi indicado na leitura de https://www.ime.usp.br/~hitoshi/introducao/15-funcao01.pdf 

```
int main() {
  float pot, x ;
  int cont , n ;
  cont = 0; pot = 1;
  cin >> n; 
  while ( cont < n ) {
     pot = pot ∗ x ;
     cont = cont + 1;
  }
  /∗ no final, a variavel pot contem x elevado a n ∗/
  cout << ...
  ...
}
```

2. Escreva uma função que calcula n!

3. Escreva um programa que leia dois inteiros m e n, com m>= n, e calcula C(m,n) = m! / n!(m-n)! Usar função da questão 2.
