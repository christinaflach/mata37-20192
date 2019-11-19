# Funções recursivas

## Fatorial de n

```
int fat(int n){
  if (n == 0) 
    return 1;
  
  return n*fat(n-1);
}
```

### Versão sem recursão
```
int fat(int n){
  int i = 0; 
  int f = 1;
  for (i=1; i <=n; i++) 
    f *= i;
  return f;
}
```

