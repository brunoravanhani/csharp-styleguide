# Guia para código C#

Meu Style Guide para desenvolvimento C# com base em clean code

A proposta desse guia é documentar uma série de preferencias pessoais e aprendizados partindo dos conhecimentos escritos no Clean Code, mas usando a linguagem C#. A proposta inicial é o uso pessoal, mas fique à vontade para usar o que for válido e sugerir melhorias.

## Verificações rápidas no contexto de um método
As duas principais coisas para avaliar um método é: está coberto de testes, ou seja, está fazendo corretamente aquilo que se propõe a fazer; e está fazendo apenas uma coisa, segundo o princípio [SRP](https://en.wikipedia.org/wiki/Single-responsibility_principle).

1. **Ter testes**
    - 100% de Code coverage, se for possível.
2. **Indentação**
    - Verificar se existe algum comando, chave ou qualquer instrução fora da indentação
    - Verificar se há mais de 2 níveis de indentação em um método (isso é um sinal de que o método pode estar fazendo mais de uma coisa):
      ```csharp
      public void DoSomething(bool parameter)
      {
        for (var p in parameters) // 1º Nível
        {
          if (!p) // 2º Nível
          {
            // p.Something() -> 3º Nível -> extrair método 
            DoOtherThing(); // 3º Nível -> método extraído
          }
        }
      }
      ```
3. **Métodos com mais de 4 instruções**
    - Não é exato, pois depende muito da instrução, mas se for muito mais que isso, é bem provável que o método está fazendo coisas demais;
    - Podemos também avaliar se a quantidade de linhas é maios que 6 ou 7.
4. **Número dos parâmetros em métodos**
    - O ideal é nenhum parametro;
    - 1 parâmetro é tranquilo;
    - 2 parametros é aceitável, mas tente dimínuir;
    - 3 parâmetros, precisa pensar bem antes de criar esse método, busque diminuir, se possível crie um objeto que inclua 2 ou mais parâmetros;
    - Mais de 3 parâmetros em raríssimos casos.
5. **Nível de abstração em método**
    - Um método deve ter apenas 1 nível de abstração;
    - Se houver mais alguma linha com outro nível, essa linha deve ser extraída;
    - Um arquivo (quase sempre) deve ter apenas uma linguagem, seja C#, javacript, HTML, Português, Inglês, etc.

## Verificações rápidas em uma classe

1. **Número de instancias privadas na classe**
    - Normalmente quando há muitas variáveis de instância em um classe, ela está fazendo coisas de mais;
    - Há um regra que diz que uma classe deve ser descrita em até 25 palavras e sem usar as palavras "se", "e", "ou" ou "mas".


## Verificações de nomeclatura

## Outras Verificações mais específicas
- Cada instrução em uma linha
- Uso correto de logs
- Comentários
- Valores "mágicos" como constantes
