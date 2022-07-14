# Aula 27 - Introdução à Razor

## Sintaxe

`Razor` utiliza uma sintaxe muito similar a ASP.

**Razor:**

```cshtml
<ul>
    @for (int indice = 0; indice < 10; indice++) {
        <li>@indice</li>
    }
</ul>
```

**ASP:**

```asp
<ul>
    <%for indice = 0 to 10%>
        <li><%=indice%></li>
    <%next%>
</ul> 
```

### Principais regras

- Blocos de código Razor são incluídos em `@{ }`;
- Expressões em linha (variáveis ​​e funções) começam com `@`;
- As instruções de código terminam com ponto e vírgula;
- As variáveis ​​são declaradas com a palavra-chave `var`;
- A `string` é colocadas entre aspas;
- O código C# diferencia maiúsculas de minúsculas;
- Os arquivos C# têm a extensão `.cshtml`.

**Exemplo**

```cshtml
<!-- Bloco de instrução única -->
@{ var Mensagem = "Hello World"; }

<!-- Expressão ou variável embutida -->
<p>O valor da variável Mensagem é: @Mensagem</p>

<!-- Bloco de várias instruções -->
@{
    var Saldacao = "Bem-vindo à nosso site!";
    var DiaDaSemana = DateTime.Now.DayOfWeek;
    var Mensagem = Saldacao + " Aqui no Rio de Janeiro é: " + DiaDaSemana;
}
<p>Resultado da mensagem é: @Mensagem</p>
```

## Variáveis

```cshtml
// Usando a palavra-chave var:
var Saldacao = "Bem-vindo à Digital House";
var counter = 103;
var today = DateTime.Today;

// Using data types:
string greeting = "Bem-vindo à Digital House";
int counter = 103;
DateTime today = DateTime.Today;
```

### Tipos

Abaixo está uma lista de tipos de dados comuns:


| Tipo  | Exemplo |
| --- | --- |
| int | 103, 12, 5168 |
| float | 3.14, 3.4e38 |
| decimal | 1037.196543 |
| bool | true, false |
| string | "Willian", "DH" |

## Converter tipos

**Int**

- AsInt()
- IsInt()

**Float**

- AsFloat()
- IsFloat()

**Decimal**

- AsDecimal()
- IsDecimal()

**DateTime()**

- AsDateTime()
- IsDateTime()

**Bool**

- AsBool()
- IsBool()

**String**

- ToString()

## Operadores

Um operador informa ao ASP.NET que tipo de comando executar em uma expressão.

A linguagem C# oferece suporte a muitos operadores. Abaixo está uma lista de operadores comuns:

| Operador | Exemplo |
| --- | --- |
| = | i=6 |
| + | i=5+5 |
| - | i=5-5 |
| * | i=5*5 |
| / | i=5/5 |
| += | i+=1 |
| -= | i-=1 |
| == | if(i==10) |
| != | if(i!=10) |
| < | if(i<10) |
| > | if(i>10) |
| <= | if(i<=10) |
| >= | if(i>=10) |
| . | DateTime.Hour |
| () | (i+5) |
| () | x=Add(i,5) |
| [] | array[3] |
| ! | if(!okay) |
| && | if(okay && valido) |
| || | if(okay || valido) |

## `if...else`

Um recurso importante das páginas da Web dinâmicas é que você pode determinar o que fazer com base nas condições.

A maneira comum de fazer isso é com as instruções `if ... else`:

```cshtml
@{
    var txt = "";

    if(DateTime.Now.Hour > 12)
    {
        txt = "Good Evening";
    }
    else
    {
        txt = "Good Morning";
    }
}
<html>
    <body>
        <p>The message is @txt</p>
    </body>
</html>
```

## `Switch`

```cshtml
@{
    var DiaDaSemana=DateTime.Now.DayOfWeek;
    var Hoje=DiaDaSemana.ToString();
    var Mensagem="";
}
<html>
<body>
@switch(Hoje)
{
    case "Monday":
        Mensagem="Este é o primeiro dia da semana.";
        break;
    case "Thursday":
        Mensagem="Apenas um dia antes do fim de semana.";
        break;
    case "Friday":
        Mensagem="Sextou!";
        break;
    default:
        Mensagem="Hoje é " + Hoje;
        break;
}
<p>@Mensagem</p>
</body>
</html>
```

## `DateTime`

```cshtml
<table border="1">
    <tr>
        <th width="100px">Nome</th>
        <td width="100px">Valor</td>
    </tr>
    <tr>
        <td>Day</td>
        <td>@DateTime.Now.Day</td>
    </tr>
    <tr>
        <td>Hour</td>
        <td>@DateTime.Now.Hour</td>
    </tr>
    <tr>
        <td>Minute</td>
        <td>@DateTime.Now.Minute</td>
    </tr>
    <tr>
        <td>Second</td>
        <td>@DateTime.Now.Second</td>
    </tr>
</table>
```

## Estrutura de repetição

Se você precisar executar as mesmas instruções repetidamente, poderá programar uma estrutura de repetição.


### `for`

```cshtml
<html>
<body>
    @for(var Indice = 10; Indice < 21; Indice++)
    {
        <p>Linha @Indice</p>
    }
</body>
</html>
```

### `foreach`

```cshtml
@{ 
    string[] Frutas = {"Banana", "Abacaxi", "Uva"}  
}
<html>
<body>
    @foreach (var Fruta in Frutas)
        {<li>@Fruta</li>}
</body>
</html>
```

### `while`

```cshtml
<html>
<body>
@{
    var contador = 0;
    while (contador < 5)
    {
        contador += 1;
        <p>Número: @contador</p>
    }
}
</body>
</html>
```