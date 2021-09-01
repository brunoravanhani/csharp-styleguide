# Guia para código C#

Meu Style Guide para desenvolvimento C# com base em clean code

A proposta desse guia é documentar uma série de preferencias pessoais e aprendizados partindo dos conhecimentos escritos no Clean Code, mas usando a linguagem C#. A proposta inicial é o uso pessoal, mas fique à vontade para usar o que for válido e sugerir melhorias.

Esse guia é separado em 3 partes:

- Verificações rápidas em uma classe - são 5 passos para verificar, dentro de uma classe, se a própria classe ou algum método está fazendo coisas demais e precisa e uma extração;
- As regras, que são 10 direcionamentos sobre o que fazer e não fazer, também no contexto de uma classe; e
- As heurísticas, dicas e code smells que são coisas que podemos melhorar no código para deixar o código melhor para o coleginha programador.

## Verificações rápidas em uma classe

1. **Indentação**
    - Verificar se existe algum comando, chave ou qualquer instrução fora da indentação
    - Verificar se há mais de 2 níveis de indentação em um método:
      ```csharp
      public void DoSomething(bool parameter)
      {
        if (parameter) // 1º Nível
        {
          if (!parameter) // 2º Nível
          {
            DoOtherThing(); // 3º Nível -> extrair método
          }
        }
      }
      ```
2. **Métodos com mais de 5 instruções**
3. **Número dos parâmetros em métodos**
4. **Número de instancias privadas na classe**
5. **Nível de abstração em método**
