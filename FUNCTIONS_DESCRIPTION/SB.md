<h1 align="center"> SB </h1>

---

#### As funções do tipo ` SB `, servem para criar messagebox usando a api do windows.h e também permitem o uso de sons do sistema diretamente no seu programa. 

#### <p align="center"> <a href="https://github.com/AllisonJunior/allen.h/tree/main" title="Retornar a documentação."> VOLTAR PARA O DOCUMENTO PRINCIPAL</a> </p>

---








<br>

<h3 align="center"> int SB_CREATEBOX ( LPCTSTR BOX_TEXT , LPCTSTR BOX_CAPTION, UINT BOX_TYPE ) </h3> 

<br>
<br>

- **O QUE ELA FAZ**: `Cria uma messagebox padrão do windows com botões e textos específicos`;

<br>

#### MACROS PARA ESSA FUNÇÃO:

```txt
Listagem dos MACROS da api do windows que podem ser usados em UINT BOX_TYPE:

> TIPOS DE MESSAGEBOX:

MB_OK:               Exibe apenas o botão "OK".
MB_OKCANCEL:         Exibe os botões "OK" e "Cancelar".
MB_ABORTRETRYIGNORE: Exibe os botões "Abortar", "Repetir" e "Ignorar".
MB_YESNOCANCEL:      Exibe os botões "Sim", "Não" e "Cancelar".
MB_YESNO:            Exibe os botões "Sim" e "Não".
MB_RETRYCANCEL:      Exibe os botões "Repetir" e "Cancelar".

> ICONES DA MESSAGEBOX:

MB_ICONHAND:                Exibe um ícone de mão com um "X" vermelho.
MB_ICONQUESTION:            Exibe um ícone de ponto de interrogação.
MB_ICONEXCLAMATION:         Exibe um ícone de ponto de exclamação.
MB_ICONASTERISK:            Exibe um ícone de asterisco.
IDICONSTOP ou IDICONERROR:  Ícone de erro (X vermelho)
IDICONQUESTION:             Ícone de interrogação (?)
IDICONEXCLAMATION:          Ícone de exclamação (!)
IDICONINFORMATION:          Ícone de informação (i)

> DEFINIÇÕES:

MB_DEFBUTTON1:  Define o primeiro botão (esquerda) como o botão padrão.
MB_DEFBUTTON2:  Define o segundo botão como o botão padrão.
MB_DEFBUTTON3:  Define o terceiro botão como o botão padrão.
MB_DEFBUTTON4:  Define o quarto botão como o botão padrão.
MB_APPLMODAL:   Especifica que a caixa de mensagem deve ser modal para a aplicação atual.
MB_SYSTEMMODAL: Especifica que a caixa de mensagem deve ser modal para todo o sistema.
MB_TASKMODAL:   Especifica que a caixa de mensagem deve ser modal apenas para a janela atual.

OBS.: Esses macros podem ser chamados sozinhos ou com mais de um assim: MACRO | MACRO2 | MACRO 3
```

<br>

#### IDS DE CONTROLE PARA ESSA FUNÇÃO:

```txt
Listagem dos IDS da api do windows que podem ser usados nessa função, para controlar ações:

IDOK -     Botão "OK"
IDCANCEL - Botão "Cancelar"
IDABORT -  Botão "Abortar"
IDRETRY -  Botão "Tentar novamente"
IDIGNORE - Botão "Ignorar"
IDYES -    Botão "Sim"
IDNO -     Botão "Não


OBS.: Esses ids servem para o seguinte:

/ int x = SB_CREATEBOX (...);

if ( x = IDOK ) printf ("Olá mundo");

```

<br>

#### CÓDIGO DE EXEMPLO:

```c

# include "allen.h"

int 
main ( void )
{      
    // Criando uma Simple box
    
    // action = Defininindo que ela retorna na variável int o clique do usuário
    // BOX_TEXT = Que o texto que irá aparecer dentro dela ira ser -> Confirme a sua presença clicando em ok!
    // BOX_CAPTION = Que o título da simple box será -> Inscrição Anual
    // BOX_TYPE = TERÁ DOIS BOTÕES ( OK E CANCELAR ) | TERÁ O ICONE DE INFORMATION | O BOTÃO PADRÃO É O SEGUNDO -> MB_OKCANCEL | MB_ICONINFORMATION | MB_DEFBUTTON2
    
    int action = SB_CREATEBOX ( "Confirme a sua presença clicando em ok!" , "Inscrição Anual" , MB_OKCANCEL | MB_ICONINFORMATION | MB_DEFBUTTON2  );

    // Executando ações
    if ( action == IDCANCEL ) echo ("Que pena que você não quis participar!");
    if ( action == IDOK )     echo ("Muito obrigado, por confirmar, segue seu codigo: 1232323");
}

```

<br>

#### SAÍDA DO CONSOLE:

<p align="center">
  <img src="https://user-images.githubusercontent.com/114815898/232237311-1ba382e0-f7cc-4be7-98c6-9b1cb4c187d8.png">
</p>

- Caso clique em cancelar: 

```txt
Que pena que você não quis participar!
```

- Caso clique em ok: 

```txt
Muito obrigado, por confirmar, segue seu codigo: 1232323
```

















<br>

<h3 align="center"> int SB_PLAYSOUND ( UINT SOUND ) </h3> 

<br>
<br>

- **O QUE ELA FAZ**: `Executa um som específico do sistema windows, definido pelo parâmetro SOUND`;

<br>

#### MACROS PARA ESSA FUNÇÃO:

```txt
Listagem dos MACROS da api do windows que podem ser usados em UINT SOUND:

MB_OK:              Som de aviso padrão. Valor padrão.
MB_ICONASTERISK:    Som de asterisco (usado no Windows XP e versões anteriores).
MB_ICONEXCLAMATION: Som de ponto de exclamação.
MB_ICONHAND:        Som de mão (usado no Windows XP e versões anteriores).
MB_ICONQUESTION:    Som de ponto de interrogação.
MB_ICONERROR:       Som de erro.
MB_ICONINFORMATION: Som de informação.
MB_ICONWARNING:     Som de aviso.
MB_ICONSTOP:        Som de parada.

OBS.: Esses macros podem ser chamados sozinhos ou com mais de um -> SB_PLAYSOUND ( MB_ICONQUESTION  | MB_OK ); 
```

<br>

#### CÓDIGO DE EXEMPLO:

```c

# include "allen.h"

int 
main ( void )
{
    PR ("Aperte qualquer tecla para reproduzir o som\n");
    getch ();

    SB_PLAYSOUND ( MB_ICONSTOP | MB_ICONWARNING );

    PR ("Som reproduzido");
}

```

<br>

#### SAÍDA DO CONSOLE:

- Antes da função:

```txt
Aperte qualquer tecla para reproduzir o som
_ <- Sinal do getch
```

- Após a função:

```txt
Aperte qualquer tecla para reproduzir o som
Som reproduzido! 
```



















