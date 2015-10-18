# [ESOF] Relatório 2 - Gestão de requisitos

<img src="Resources/logo.png" width="300px" alt="Atom"/>

## Levantamento de requisitos
Para uma compreensão detalhada do processo de levantamento de requisitos utilizado
no projeto torna-se vital compreender e distinguir as duas principais fases de
desenvolvimento do mesmo. Com efeito, o Atom começou a sua existência como
um projeto inspirado na visão do seu criador e único programador, tendo
sido eventualmente posto de parte pelo mesmo.

Apenas mais tarde seria o projeto retomado, desta vez pela empresa *GitHub*,
que adotou o modelo de *open-source* que atualmente o caracteriza. Esta adoção
operou uma mudança significativa nas metodologias de levantamento de requisitos e
sua negociação e validação, passando todo este processo a operar-se sob uma
ampla plataforma comunitária, que a par da equipa do *GitHub* se revela um dos
mais importantes *stakeholders* do produto final.

### Contexto Inicial
Dadas as circunstâncias sob as quais surgiu o projeto, explicadas em mais detalhe
no primeiro relatório, o levantamento de requisitos foi baseado na
experiência pessoal do primeiro programador do projeto, Chris Wanstrath.

Das necessidades identificadas destacam-se as seguintes, pela influência que
revelaram ter na descrição dos requisitos do projeto.<sup>[[1]](#ref1)</sup>:

* O editor de texto deve funcionar por cima de uma interface baseada em
tecnologias web;
* Deve ser possível, virtude das tecnologias web utilizadas, que todas as
funcionalidades sejam alteradas facilmente;
* Deve ser fácil de utilizar.

Do acima mencionado decorre que, no contexto do que tradicionalmente se define
como levantamento de requisitos em Engenharia de Software, ocorreu,
no que ao Atom diz respeito, uma sobreposição dos papeis tipicamente associados
ao do cliente e do engenheiro de software. Esta sobreposição fica
particularmente clara na forma como a equipa fala sobre a origem do seu projeto
em [[1]](#ref1):
> Atom started as a side project of GitHub founder @defunkt (Chris Wanstrath)
 way back in mid 2008, almost exactly seven years ago. He called it Atomicity.
> **His dream was to use web technologies to build something as customizable as
 Emacs and give a new generation of developers total control over their editor**.

Um dos efeitos mais notáveis desta sobreposição é o facto de se encontrar, neste
contexto, referências às tecnologias particulares a serem utilizadas,
pormenores técnicos que regra geral não são refletidos no

Revela-se também de grande importância para a compreensão do processo de levantamento
de requisitos usado a contextualização do Atom enquanto projeto *open-source*,
cujas características não-comerciais e de estruturação das equipas de desenvolvimento
tornam, na nossa perspectiva, difícil a aplicação de modelos convencionais de
levantamento de requisitos, sendo exigidos novos métodos que permitam abarcar
a natureza descentralizada e colaborativa dos utilizadores e dos contribuidores
para o projeto.


#### Das necessidades aos requisitos <sup>[[2, pg 6]](#ref2)</sup>
Os requisitos até agora listados são uma análise não sistematizada nem
formalizada das necessidades identificadas pelo cliente. Não foi possível,
analisando a documentação disponível ou pela comunicação com os responsáveis
pelo projeto, chegar aos requisitos de sistema identificados. É aliás altamente
improvável que, dado o contexto de desenvolvimento inicial, os mesmos tenham
sido formalizados.

Como exercício de engenharia de software segue pois uma hipotética lista
de requisitos formalizados que poderiam ter sido utilizados, agrupadas por tipo
<sup>[[2, pg 13]](#ref2)</sup>:

###### Requisitos Funcionais
* O programa deve permitir a manipulação de *buffers* de texto.
* O programa deve providenciar, para o requisito acima, uma interface similar
à de outros programas comummente utilizados para esta tarefa.
* O programa deve permitir que a interface de manipulação previamente
mencionada seja alterada conforme as necessidades do utilizador, garantindo
flexibilidade na mesma.
* O programa deve permitir que os *buffers* manipulados ou criados
sejam gravados em disco, e deve permitir a leitura de buffers gravados
em disco para que possam ser manipulados.
* O programa deve permitir a instalação de funcionalidades adicionais
providenciando ao utilizador um sistema que permita gerir as *packages*,
contendo as alterações em causa, facilitando o processo de as descarregar,
ativar/desativar e apagar.
* O programa deve providenciar suporte a funcionalidades comummente utilizadas
na área da programação ou manipulação de código, como a indentação automática
ou o realce sintático de palavras ou segmentos de texto.
* O programa deve facilitar a edição de múltiplos ficheiros em simultaneo, por meio de
tabulações e outras funcionalidades.

###### Requisitos não Funcionais <sup>[[3]](#ref3)</sup>
* Deve ser providenciada aos desenvolvedores de packages uma *framework*
de interpretação dos programas escritos em *javascript*.
* A estrutura da interface do programa deve ser especificada em *HTML* e o
seu aspeto em *CSS*, permitindo a sua interpretação pela *framework*
supramencionada.
* A plataforma deve providenciar capacidades que facilitem o desenvolvimento
do programa, como sejam um *debugger* e um *profiler* de desempenho.
* Deve permitir a recolha de dados acerca de problemas que tenham levado
a uma eventual anormal interrupção do programa.
* Deve facilitar o *deployment* de atualizações, fruto do modelo de iteração
utilizado para o desenvolvimento do programa.

### Contexto Atual
Atualmente a situação do projeto é vastamente diferente das circunstâncias em
que surgiu. O modelo open-source coloca diversos desafios no que à gestão
de requisitos diz respeito. Os métodos tradicionais da Engenharia de Software
não podem assim ser mapeados com facilidade à especificidade do projeto.

#### Elicitação de requisitos

Existem, hoje em dia, duas ferramentas principais utilizadas para fazer a elicitação
de requisitos: *issues* e *pull requests*. Ambas estas ferramentas estão disponíveis
para a equipa do *GitHub* e para o público em geral. Os *issues* servem essencialmente
para fazer chegar à atenção da comunidade a existência de uma necessidade de alteração.
Os *issues* podem, grosso modo, ser divididos em duas categorias, os que dizem
respeito a comportamento anómalo ou incorreto do programa e as que
solicitam a implementação de novas funcionalidades.

Os *pull requests* são pedidos de alterações no código-fonte, servindo
para responder a *issues* previamente identificados ou simplesmente para corrigir
*bugs* detetados e corrigidos pela pessoa que envia o *pull request*.

#### Negociação e análise

O modelo aberto acima descrito e os elevados níveis de interesse que o projeto
suscita levam a uma massificação da quantidade de requisitos levantados.
Consequentemente a **negociação e análise** dos requisitos levantados assume
uma importância ainda maior do que a que já lhe cabe na Engenharia de
Software tradicional. Se a mesma continua a ser necessária para assegurar que
o esforço de desenvolvimento se dirige para áreas tecnicamente exequíveis e
funcionalmente vantajosas, aqui assume ainda um papel decisivo na filtragem
da qualidade dos pedidos efetuados e da sua adequação aos objetivos do projeto.
A abertura ao público do contacto com a equipa de desenvolvimento leva
à necessidade de uma eficaz filtragem das solicitações, para que as mais relevantes
não se percam entre o ruído gerado pelo elevado nível de solicitações. Num dado
momento mais de 1000 *issues* podem estar abertos.<sup>[[4]](#ref4)</sup>

Do anteriormente exposto decorre uma grande necessidade de categorização e
compartimentalização dos requisitos levantados. A expansibilidade do Atom, com
recurso a *packages* permite que muita da funcionalidade de base seja implementada
sob a forma da sua própria *package* independente. Esta constitui aparentemente
a primeira linha de categorização e separação dos requisitos, já que cada *package*
conta com o seu próprio repositório e a sua própria lista de *issues* e *pull
requests*. As *packages* que implementam a funcionalidade base e que são geridas
diretamente pela equipa do Atom são designadas por *core packages*.

Requisitos que digam respeito à API do Atom, que é usada pelas *packages* para
implementar são efetuadas diretamente no repositório do Atom. Neste repositório
importa portanto negociar os requisitos solicitados com base em dois critérios:
o impacto na performance do programa da implementação de novos métodos na API e
assegurar que as alterações efetuadas mantêm o comportamento correto da API, de
que dependem as *packages* construídas sobre a mesma. Este processo será discutido
mais aprofundadamente na secção que versa sobre [Validação](#val).

A negociação de cada *issue* criado e cada *pull request* é efetuada numa secção
do mesmo, dedicada a comentários por parte da comunidade. Nela podem ser
facilmente solicitados esclarecimentos adicionais, e podem ser confirmadas
reproduções de *bugs*, sendo possível um contacto célere e desformalizado entre
desenvolvedores e os restantes *stakeholders*.

##### Priorização
Nem todos os problemas levantados pela comunidade merecem, por parte da equipa
que gere o projeto, a mesma atenção a nível de tempo e recursos. Para fazer a
triagem e escolher os assuntos sobre os quais a equipa principal do projeto
se vai focar, a mesma efetua reuniões semanais, todas as segundas-feiras,
nas quais decide como vai alocar os seus recursos ao longo da semana seguinte.

Os *issues* que sejam identificados como mais relevantes são marcados com uma
*tag* específica, assinalando que faz parte dos esforços que a equipa principal
vai desenvolver ao longo da semana.<sup>[[5]](#ref5)</sup>

>We prioritize inbound issues in our team meeting every Monday.
Anything that gets a special GitHub issue label of `atom` will be
discussed and prioritized. We try and focus on regressions and get
hotfixes out quickly.

A importância destas reuniões semanais é acentuada pelo facto de não existir um
documento oficial de especificação dos requisitos de software que permita delinear
um percurso claro para o processo de desenvolvimento.

#### <a name="val"></a> Validação
A validação de requisitos é o processo que permite aferir, relativamente a um
novo requisito, se o mesmo cumpre os critérios de qualidade e de funcionalidade
previamente determinados. Tendo em conta que para além de ser um editor de texto
o Atom é também uma API que fornece funcionalidades a *packages* independentes
este processo é essencial para garantir que o comportamento dos seus métodos
se mantém dentro das especificações e do comportamento esperado. Qualquer
alteração de comportamento inesperada pode implicar que novos *bugs* surjam em
múltiplas *packages* fornecidas por terceiros.

Posto isto, é de extrema importância que a validação das alterações à API seja
efetuada de forma rigorosa, pois o degradamento da qualidade no que diz respeito
à fiabilidade do sistema seria facilmente posto em causa pela acumulação de
*bugs* devido a alterações na API, podendo resultar em interrupções de funcionamento
do editor de texto, ou mesmo, em casos extremos, na perda de documentos.

### Análise dos Resultados
Esta abordagem parece permitir à equipa responder de forma eficaz às
solicitações de requisitos por parte da comunidade. No mês anterior,
por exemplo, a equipa conseguiu responder a mais de metade dos *issues*
abertos pela comunidade, conforme ilustrado na figura abaixo.

<img src="Resources/issues.png" width="500px" alt="Atom"/>

## Validação de requisitos
Cabe nesta área efetuar, para cada alteração ao software, uma validação quer do
cumprimento do problema ou funcionalidade que a alteração procura corrigir ou
acrescentar, quer da estabilidade estrutural do software, por forma a que não
sejam introduzidos problemas adicionais na tentativa de corrigir problemas
antigos.

### Validação do cumprimento

Tomando proveito da comunidade existente à volta do projeto, a equipa de
desenvolvimento do Atom consegue lançar novas funcionalidades, bem como
*bugfixes*, recebendo *feedback* muito mais celeremente do que seria possível
em projectos privados. Assim acabam por ser os próprios *stakeholders* a validar
que os problemas estão efetivamente corrigidos, não existindo, aparentemente, um mecanismo
formal que efetue esta verificação por parte da equipa de desenvolvimento.

### Validação da retro-funcionalidade

É vital que as correções que vão sendo introduzidas provoquem o mínimo de problemas
 possível nas componentes já desenvolvidas. Para permitir detetar estes problemas mais
facilmente o projeto usa funcionalidades do GitHub que permitem assegurar que cada *pull
request* passa uma *suite* de testes unitários.

Adicionalmente, todos os problemas que sejam introduzidos, malogrado o mecanismo de prevenção supracitado,
 são priorizados para correção nas reuniões semanais do projeto.

## Referências
<a name="ref1" href="http://blog.atom.io/2015/06/25/atom-1-0.html">1) Atom 1.0</a><br>
<a name="ref2" href="https://moodle.up.pt/pluginfile.php/68505/mod_resource/content/2/ESOF-Requirements%20Engineering.pdf">2) Slides da Unidade Curricular<br></a>
<a name="ref3" href="http://electron.atom.io/">3) Electron</a><br>
<a name="ref4" href="https://github.com/atom/atom/issues?q=is%3Aopen+is%3Aissue">4) Atom Issues</a><br>
<a name="ref5" href="https://github.com/jrfcabral/atom/blob/master/ESOF-docs/email1.md">5) Email de Kevin Sawicki</a>
