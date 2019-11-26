# Strings e Tipo `Char`

## Créditos

Adaptado a partir de:
+ [Aulas do Prof. Rodrigo Rocha (UFBA)](https://rodrigorgs.github.io/aulas/mata37/)

Material suplementar:

+ [Caracteres - Tipo char (Apostila da USP - cap 20)](https://www.ime.usp.br/~hitoshi/introducao/20-caracteres.pdf)
+ [Strings (Apostila da USP - cap 21)](https://www.ime.usp.br/~hitoshi/introducao/21-strings.pdf)

---

## Motivação 

Há informação que não é numérica, por exemplo, nome e endereço residencial são informações textuais. Textos são compostos por caracteres do alfabeto, de pontuação, acentuação, dentre outros.

Nesta parte do curso, vamos trabalhar com elementos do tipo `char` (caractere) e do tipo `string` (cadeia de caracteres).

# Tipo Char

Um caractere pode ser uma letra (maiúscula ou minúscula), um ponto final, um ponto de interrogação, enfim, um símbolo que normalmente são encontrados
no teclado do computador.

Em C, caracteres são armazenados como números inteiros.

Considere o seguinte programa:

```c++
#include <iostream>
#include <string>

using namespace std;

int main() {
  int x = 65;

  cout << x << endl;
  
  return 0;
}
```

Agora troque `int` por `char`. O que acontece?


## Tabela ASCII

Cada caractere é codificado através de um byte, ou seja, um número entre 0 e 255. A correspondência entre valor numérico e caractere é dada pela [tabela ASCII](https://www.asciitable.com/).

Assim, `char x = 'A';` e `char x = 65;` são equivalentes.

Quando se digita a letra A no teclado, o computador armazena na memória o número inteiro 65.

## Declaração de variável do tipo `char`

Declaração de uma variável do tipo char de nome "ch":

```char ch;```

## Caracteres de controle

Os caracteres com código decimal entre 0 e 31 são chamados de caracteres de controle. Exemplos: 

+ `linefeed` tem código 10 e tem como significado "pula uma linha"
+ `carriage return` tem código 13 e tem como significado "o cursor vai para a primeira coluna"

## Leitura e impressão de caracteres em C

Ler [capítulo 20 do material da USP](https://www.ime.usp.br/~hitoshi/introducao/20-caracteres.pdf).
Observar que são usadas as funções scanf e printf de C no material acima.

## Exercícios

### Exercício 1

Faça um programa em C que imprima todos os caracteres cujo códigos ASCII estão entre 32 e 126.

### Exercício 2

Faça um programa em C que lê caracteres do teclado e, para cada caractere lido, imprime se o mesmo é letra maiúscula, 
letra minúscula, dígito ou outro qualquer.

### Exercício 3

Leia uma sequência de caracteres terminada por um ponto ’.’ a partir do teclado (representando uma frase), 
e determine a frequência relativa de vogais no texto (por exemplo, no texto “Em terra de cego quem tem um olho é caolho”, 
essa frequência é 16/42).

### Exercício 4

Dada uma frase terminada por ’.’, imprimir o comprimento da palavra mais longa.

### Exercício 5

Dada uma frase terminada por ’.’, 
determinar quantas letras e quantas palavras aparecem no texto. 
Por exemplo, no texto “O voo GOL547 saiu com 10 passageiros.” 
há 25 letras e 7 palavras.

## Operações sobre o tipo char (C++)

Use `#include <cctype>`. 

- `tolower(c)` - converte para minúsculas
- `toupper(c)` - converte para maiúsculas
- `isalnum(c)` - checa se é alfanumérico
- `isalpha(c)` - checa se é uma letra do alfabeto
- `isdigit(c)` - checa se é um dígito numérico
- `isblank(c)` - checa se é um caracter em branco (espaço, tab, quebra de linha...)
- e [outras](http://www.cplusplus.com/reference/cctype/)...

### Exercício 6

Refazer o exercício 2 em C++, usando as operações sobre o tipo char.

---

# Strings em C

No curso, usaremos exemplos em C++ para trabalhar com strings. Para leitura complementar, se houver interesse, o capítulo 21 do material sobre [Strings em C](https://www.ime.usp.br/~hitoshi/introducao/21-strings.pdf) da USP apresenta conceitos e exemplos sobre manipulação de strings em C com a biblioteca de funções para manipular strings _string.h_.

# Strings em C++

## Leitura de strings

```c++
string x;

getline(cin, x);
cin >> x;
```

## Leitura de strings

`cin >>` lê a entrada até encontrar um caractere de espaço em branco (_caractere de controle_ como espaço, tab, quebra de linha, etc.), mas **não remove esse caractere da entrada**.

`getline(cin, variavel)` lê a entrada até encontrar uma quebra de linha, e **remove a quebra de linha da entrada**. 
A variável recebe todo o conteúdo antes da quebra de linha.


## Leitura de strings

Isso causa problemas ao usar o `getline` após o `cin >>`. 
Para resolver, use `cin.ignore()` (descarta o próximo caractere da entrada) ou então `cin >> ws` (descarta todos os caracteres em branco consecutivos da entrada):

```c++
int idade;
string nome;

cin >> idade;
cin.ignore();
getline(cin, x);
```

## Fim de arquivo (EOF, end-of-file)

Para saber se a entrada acabou, use `cin.eof()`.
Se a entrada é do teclado, o "fim de arquivo" é obtido pressionando Ctrl+D (Linux, Mac) ou Ctrl+Z, Enter (Windows).

 Ex.:

```c++
// Programa que lê uma linha e imprime a linha lida, até
// encontrar o final da entrada.
#include <iostream>
#include <string>

using namespace std;

int main() {
  string x;

  while (!cin.eof()) {
    getline(cin, x);
    cout << x << endl;
  }

  return 0;
}
```

---

## Operações básicas com strings

- `str.length()` ou `str.size()` - retorna comprimento de `str`
- `str[indice]` - acessa caractere na posição `indice`
- `str[indice] = c` - altera caractere na posição `indice`
- `str1 += str2` - insere `str2` no final de `str1` (concatenação)
- `str1 == str2` - comparação de igualdade
- `str1 < str2` - comparação de ordem alfabética (mais ou menos)

---

## Outras operações com strings

- Extrair uma porção da string (`substr`)
- Encontrar a primeira ocorrência de uma string em outra (`find`)

---

## Substrings

`str.substr(pos, comprimento)` - retorna uma nova string com `comprimento` caracteres a partir da posição `pos`. 



## Busca em strings

- `str.find(trecho)`
- `str.rfind(trecho)`

Retorna posição da primeira (`find`) ou da última (`rfind`) ocorrência de `trecho` dentro de `str`.

Ex.:

```c++
string frase = "o rato roeu a roupa";
string palavra = "rato";
cout << frase.find(palavra) << endl;
// saída: 2
```



## Busca em strings

- `str.find(trecho)`
- `str.rfind(trecho)`

O retorno é do tipo size_t (que é efetivamente um inteiro sem sinal).
Se o trecho **não for encontrado**, retorna `string::npos`. 

Ex.:

```c++
string frase = "o rato roeu a roupa";
string palavra = "Roma";
size_t pos = frase.find(palavra);
if (pos == string::npos) {
  cout << "Palavra não encontrada na frase";
} else {
  cout << "Posição " << pos;
}
cout << endl;
```

## Busca em strings

Opcionalmente, pode-se passar um parâmetro a mais, `posicao`:

- `str.find(trecho, posicao)` - busca o trecho a partir da posição `posicao`.
- `str.rfind(trecho, posicao)` - busca o trecho considerando apenas sequências de caracteres iniciadas na posição `posicao` ou posições anteriores.

---

## Exemplo: extrair dados de arquivo HTML

Dada uma string, extraia cada trecho contido entre as tags `<b>` e `</b>` e imprima um trecho por linha.

```c++
#include <iostream>
#include <string>

using namespace std;

int main() {
  string frase = "Oi, <b>Fulano</b> de <b>SSA</b>";
  size_t ini = 0;
  size_t fim = 0;

  while (ini != string::npos) {
    ini = frase.find("<b>", ini);
    if (ini != string::npos) {
      fim = frase.find("</b>", ini + 1);
      if (fim != string::npos) {
        cout << frase.substr(ini + 3, fim - ini - 3) << endl;
        ini = fim + 1;
      }
    }
  }

  return 0;
}
```

