# ead_php_alura_design-pattern-comportamental

> Projeto referente a [este](https://cursos.alura.com.br/course/php-design-pattern-comportamental) curso.

1. Crie o ambiente
```sh
docker-compose up -d
```
> Caso queira, ao final da configuração, pare o Docker com ``docker-compose down``

2. Crie o autoloader
```sh
docker-compose exec app composer du
```

## Execução

- Caso recém tenha feito a **configuração inicial** e o ambiente continue rodando, tudo certo. Pode acessar ``localhost:8989/arquivo-script.php``
- Do contrário, suba o ambiente novamente:
```sh
docker-compose up
```
> Pare com <kbd>Ctrl</kbd><kbd>C</kbd>

> Caso modifique Dockerfile, rebuilde com ``docker-compose up --build``

> Para acessar o container use ``docker-compose exec app bash`` ou execute os scripts diretamente pelo Docker ``docker-compose exec app php public/arquivo-script.php``

## Anotações

Padrões comportamentais tratam da comunicação e designação da responsabilidade de vários objetos, se comunicando entre si, trocando responsabilidades entre si.

---

- **Strategy** cria um conjunto de classes de mesma interface que encapsulam um algoritmo. Evita criação de *ifs*, pois a classe é passada como parâmetro
- **Chain of Responsibility** quando a lógica a ser feita é em tempo de execução, diferente da strategy que é simples escolher a classe correta para usar como parâmetro,  podemos "encadear" os ifs que devem ser resolvidos
- **Template Method** cria uma classe abstrata que força implementação de algu(ns) método(s), permite a sobescrita de métodos existentes e cria um método padrão que executa na ordem correta os métodos.
- **State** mistura de template (definição se métodos obrigatórios ou que podem ser sobescritos) com chain (um estado conhece/retorna o outro)
- **Command** classe especializada em somente uma tarefa (chamada de services, usecases e commandhandler)
- **Observer** adiciona "eventos" que implementam uma mesma interface, tornando alguma classe mais extensível. Não faz muito sentido usar com um commnand, talvez com repository, log e etc
- **Iterator** cria uma classe que é uma coleção de alguma outra classe. Essa coleção é "percorrível" com `foreach`
