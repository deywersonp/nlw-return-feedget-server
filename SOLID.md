# SOLID

1. Single Responsibility Principle
2. Open/Closed Principle
3. Liskov Substitution Principle
4. Interface Segregation Principle
5. Dependency Inversion Principle

-----------------

1. Cada classe tem uma responsabilidade única;
  Q.1: Como saber se estou ferindo esse principio?
  A.1: Se ao tentar explicar a função para alguém (e.g criar feedback) você utilizar um E, isso é um ponto de atenção. E.g: A minha função de criar feedback ela cria um feedback E envia um email ← Note que aqui utilizamos um E, ponto de atenção!

2. As classes da aplicação devem ser abertas para extensão mas fechadas para modificação;
  2.1. Esse é um principio mais voltado para a orientação em objetos, dificilmente será algo com o qual vamos nos preocupar, mas basicamente esse principio diz que: Se eu tenho uma classe, e eu faço um extend dessa classe, eu não posso mudar o funcionamento dela, apenas extender sua aplicação.

3. Nós devemos poder substituir uma classe pai por uma herança dela e tudo continuar funcionando;
  3.1. Vamos supor que tenhamos a classe Ave e a classe Gavião. Deveria ser possível colocar a classe Gavião na classe Ave e tudo continuar funcionando, independente da classe Gavião ter mais funcionalidades que a classe Ave;

4. Consiste em tentar separar as interfaces o máximo possível, e.g: 
  Temos uma Impressora. Essa Impressora pode: Imprimir, Scannear, Digitalizar, etc...
  Transformando isso para uma classe teríamos:
  class Impressora implements [...]
  O recomendado seria: 
  class Impressora implements Imprimir, Digitalizar, Scannear

  ao invés de:
  class Impressora implements TodasAsFuncoesDeUmaImpressora

5. Fica mais prático com exemplo, vamos lá:
  Nossa rota de criação de feedback ela hoje depende do Nodemailer, pois é ele que faz o envio do email, ela depende de algo externo;
  O correto é ao invés da classe buscar as dependências que ela precisa, o contexto externo fala pra ela quais dependências ela vai utilizar;
  Ele é um principio muito importante e faz toda a diferença, além de nos auxiliar quando estamos trabalhando com testes;
  Normalmente quando estamos testando, o nosso objetivo muitas vezes não é registrar uma informação no banco de dados, fazer o envio de email, mas sim verificar a regra de negócio que foi escrita.
  