
# Estruturas de seleção

As estruturas de seleção determinam quais linhas de código serão executadas de acordo com alguma condição.

Em C/C++, as principais estruturas de seleção são as seguintes:

- `if` (`if`-`else`, `if`-`else if`...)
- `switch`
- operador ternário (`? :`)

---

## Comando break

O comando _break_ realiza um desvio incondicional, com dois usos mais conhecidos:

   1. Saída de um comando _switch..case_ (mostrado a seguir).
   2. Saída de um laço de repetição

## Comando switch

```c++
switch (expressão) {
    case valorA:
        instrucaoA1;
        ...
        instrucaoAN;
        break;
    case valorB:
        instrucaoB1;
        ...
        instrucaoBN;
        break;
    case valorN:
        instrucaoN1;
        ...
        instrucaoNN;
        break;
    default:
        intrucaoD1;
        ...
        instrucaoDN;
}
```

---

## switch

Se esquecer de escrever o _break_, a execução continua nas instruções do próximo `case` (o que pode ser desejado ou não).




