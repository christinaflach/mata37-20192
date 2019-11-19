# Funções recursivas

## Fatorial de n

### Uma versão sem recursão
```
int fat(int n){
  int i = 0; 
  int f = 1;
  for (i=1; i <= n; i++) 
    f *= i;    // f = f * i;
  return f;
}
```

### Versão recursiva

```
int fat(int n){
  if (n == 0) 
    return 1;
  
  return n * fat(n-1);
}
```

## Série de Fibonacci (0,1,1,2,3,5,8,13,...)

### Versão sem recursão

```
int fib(int n){
  int f1 = 0, f2 = 1;
  int f3, i; 
  for (i=1; i <= n; i++) { // versão iterativa
    f3 = f2+f1;
    f1 = f2; 
    f2 = f3;
  }
  return f1; 
}
```


### Versão recursiva

```
int fib(int n){
  if (n <= 1) 
    return n;
  return fib(n-1) + fib(n-2);
}
```

## Torres de Hanoi

Pesquisar.
