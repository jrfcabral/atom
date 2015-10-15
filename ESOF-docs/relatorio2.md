# [ESOF] Relatório 2 - Gestão de requisitos

<img src="Resources/logo.png" width="300px" alt="Atom"/>

## Levantamento de requisitos
Dadas as circunstâncias sob as quais surgiu o projeto, explicadas em mais detalhe no primeiro relatório, o levantamento de requisitos foi baseado na experiência pessoal 
do primeiro programador do projeto, Chris Wanstrath.

Destes requisitos destacam-se os seguintes, por serem instrumentais na definição dos tipos de requisitos que têm vindo a ser solicitados<sup>[1](#ref1)</sup>:

* O editor de texto deve funcionar por cima de uma interface baseada em tecnologias web
* Deve ser possível, virtude das tecnologias web utilizadas, que todas as funcionalidades sejam alteradas facilmente
* Deve ser fácil de utilizar

Do acima mencionado decorre é possível concluir que, no contexto do que tradicionalmente se define como levantamento de requisitos em Engenharia de Software, ocorre,
no que ao Atom diz respeito, uma sobreposição dos papeis tipicamente associados ao do cliente e do engenheiro de software. Conforme se pode

[You can use numbers for reference-style link definitions][1]

### *Issues* do GitHub
O projeto usa a interface de issues do GitHub para recolher os diversos problemas e solicitações de funcionalidades que vão sendo formuladas pelos utilizadores do programa.

### Priorização
Nem todos os problemas levantados pela comunidade merecem, por parte da equipa que gere o projeto, a mesma atenção a nível de tempo e recursos. Para fazer a triagem e escolher os assuntos sobre os quais a equipa principal do projeto se vai focar, a mesma efetua reuniões semanais, todas as segundas-feiras, nas quais decide como vai alocar os seus recursos ao longo da semana seguinte.

### Abordagem ao desenvolvimento
Qualquer membro da comunidade de desenvolvimento do Atom pode trabalhar em qualquer um dos requisitos elicitados na secção de *Issues*. 

A equipa principal, contudo, foca-se em resolver os assuntos levantados na reunião supramencionada, cujos *Issues* correspondentes estão marcados com uma *tag* especial que os assinala como prioritários.

### Análise dos Resultados
Esta abordagem parece permitir à equipa responder de forma eficaz às solicitações de requisitos por parte da comunidade. No mês anterior, por exemplo, a equipa conseguiu responder a mais de metade dos *issues* abertos pela comunidade, conforme ilustrado na figura abaixo.

<img src="Resources/issues.png" width="500px" alt="Atom"/>

## Validação de requisitos
Cabe nesta área efetuar, para cada alteração ao software, uma validação quer do cumprimento do problema ou funcionalidade que a alteração procura corrigir ou acrescentar, 
quer da estabilidade estrutural do software, por forma a que não seja introduzidos problemas adicionais na tentativa de corrigir problemas antigos.

### Validação do cumprimento

Tomando proveito da comunidade existente à volta do projeto, a equipa de desenvolvimento do Atom consegue
lançar novas funcionalidades, bem como *bugfixes*, recebendo *feedback* muito mais celeremente do que seria possível em projectos 
privados. Assim acaba por ser os próprios *stakeholders* a validar que os problemas estão efectivamente corrigidos, não existindo um mecanismo formal
que efetue esta verificação por parte da equipa de desenvolvimento.

### Validação da retro-funcionalidade

É vital que as correções que vão sendo introduzidas provoquem o mínimo de problemas
 possível nas componentes já desenvolvidas. Para permitir detetar estes problemas mais
facilmente o projeto usa funcionalidades do GitHub que permitem assegurar que cada *pull
request* passa uma *suite* de testes unitários. 

Adicionalmente, todos os problemas que sejam introduzidos, malogrado o mecanismo de prevenção supracitado,
 são priorizados para correção nas reuniões semanais do projeto.

## Referências
<a name="ref1" href="http://blog.atom.io/2015/06/25/atom-1-0.html">Atom 1.0</a>