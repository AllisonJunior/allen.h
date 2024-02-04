<h1 align="center"> LOCH </h1>

---

#### As funções do tipo ` LOCH `, servem para definir o padrão de texto, atributos, padrões, acentuações, etc do console. Em outras palavras são 2 funções que definem a região do console usando a biblioteca locale.h.  

#### <p align="center"> <a href="https://github.com/AllisonJunior/Random/tree/d18f674d1beaec2fbd48c33c0551cd901f1bcd3d/Projetos/C/%5B%20C%20%5D%20allen.h%20-%20Primeira%20vers%C3%A3o%20da%20biblioteca%20allen" title="Retornar a documentação."> VOLTAR PARA O DOCUMENTO PRINCIPAL</a> </p>

---








<br>

<h3 align="center"> void LOCH_LOCAL ( void ) </h3> 

<br>
<br>

- **O QUE ELA FAZ**: `Essa função define que o console irá utilizar o padrão português brasileiro, nada mais é do que setlocale (LC_ALL, "");`;

<br>

#### CÓDIGO DE EXEMPLO:

```c

# include "allen.h"

int 
main ( void )
{   
    // Texto em português
    LOCH_LOCAL ();
    
    printf ("Acentuação");
}

```

<br>

#### SAÍDA DO CONSOLE:

```txt
Acentuação
```

























<br>

<h3 align="center"> void LOCH_SETLOCAL ( char REGION [] ) </h3> 

<br>
<br>

- **O QUE ELA FAZ**: `Essa função define que o console irá utilizar algum padrão de linguagem que pode ser definido em setlocale pelo usuário `;

<br>

#### CÓDIGO DE EXEMPLO:

```c

# include "allen.h"

int 
main ( void )
{   
    // Definindo o console para português
    LOCH_SETLOCAL ( "portuguese_brazil" );

    printf ("Acentuação");
}

```

<br>

#### SAÍDA DO CONSOLE:

```txt
Acentuação
```
