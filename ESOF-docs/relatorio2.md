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
pormenores técnicos que, regra geral, não são providenciados quando lidando com clientes com uma compreensão e conhecimento das tecnologias e técnicas necessárias à elaboração de software limitados.

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

#### Diagrama de Casos de Uso
<img src="https://raw.githubusercontent.com/jrfcabral/atom/master/ESOF-docs/Resources/UseCaseAtom.jpg">

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

#### <a name="val"></a> Validação de requisitos
A validação de requisitos é o processo que permite aferir, relativamente a um
novo requisito, se o mesmo corresponde ao sistema que o cliente efetivamente
pretende<sup>[[2, pg 31]](#ref2)</sup>. No caso do Atom, como de muitos outros
projetos *open-source* o papel do cliente é desempenhado pela mesma equipa a quem
cabe a validação dos requisitos. Assim é o próprio cliente que é responsável
por assegurar que os requisitos que traça correspondem às suas reais
necessidades.

Tendo em conta que para além de ser um editor de texto
o Atom é também uma API que fornece funcionalidades a *packages* independentes
este processo é essencial para garantir que o comportamento dos seus métodos
se mantém dentro das especificações. Qualquer alteração de comportamento
inesperada pode implicar que novos *bugs* surjam em múltiplas *packages*
fornecidas por terceiros. Pode-se pois considerar que a necessidade central
do cliente é a existência de uma API bem especificada e estável.

Posto isto, é de extrema importância que a validação dos novos requisitos
cuja implementação implique alterações à API seja efetuada de forma rigorosa,
pois o degradamento da qualidade no que diz respeito à fiabilidade do sistema
seria facilmente posto em causa pela acumulação de *bugs* devidos a alterações
na API, podendo resultar em interrupções de funcionamento
do editor de texto, ou mesmo, em casos extremos, na perda de documentos.

O Atom implementa, em primeira instância, a validação dos seus requisitos ao
nível da discussão que é feita em cada *issue* novo que surge. O processo
de categorização, implementado em larga medida pela equipa de desenvolvedores
principais permite rapidamente categorizar os pedidos que não passam de meras
correções de *bugs*, não suscetíveis de provocar alterações indesejáveis
ao nível da estabilidade.

A segunda instância de validação de requisitos ocorre ao nível da interface
de *pull requests*. O projeto faz uso de uma plataforma de testes, a *Travis CI*,
integrada na funcionalidade do GitHub que valida automaticamente cada *pull request*,
assegurando que cumpre a especificação testada por um conjunto de casos de teste.
Para além disso é também possível ao desenvolvedor de cada *package* usar esta
plataforma para efetuar testes ao seu software.<sup>[[6]](#ref6)</sup>.

É possível que, malogradas todas as precauções de validação acima detalhadas,
um novo requisito provoque alterações indesejadas ao comportamento da API,
deixando o programa de corresponder ao sistema desejado pelo cliente. Neste caso
os vários *stakeholders* do projeto podem expressar o problema criado usando
a interface de *issues* previamente detalhada.

## Conclusão
Os métodos de gestão de requisitos aplicados ao projeto diferem de forma significativa
daqueles que são abordados nas aulas da Unidade Curricular de Engenharia de Software.
Com efeito, a natureza open-source e aberta do projeto e a dimensão da sua
base de utilização e a diversidade de casos de uso que a implementação de uma
API para *packages* de desenvolvedores externos à equipa central permite torna
extremamente difícil que a elicitação de requisitos se processe pelos métodos
tradicionais.

Pelas características acima explicadas da base de utilizadores do projeto seria
extremamente complicada a aplicação de técnicas de entrevista que permitissem
chegar a uma opinião representativa da maioria dos utilizadores.<sup>[[2, pg 35]](#ref2)</sup>

Por outro lado devem ser consideradas as fragilidades do método de
aplicação de questionários aos utilizadores. Devido à sua estrutura fechada
este método de elicitação de requisitos revela-se de utilidade limitada
para o levantamento de requisitos novos ou
inovadores.<sup>[[2, pg 37]](#ref2)</sup>

A metodologia pode ser interpretada como uma alteração do método de brainstorming.<sup>[[2, pg 36]](#ref2)</sup>
É um processo aberto à comunidade em geral onde todas as ideias têm uma plataforma
para a sua expressão ao público. O processo de combinação e melhoramento de [ideias
ocorre livremente](https://github.com/atom/tree-view/issues/55), possibilitando
o aparecimento de novos requisitos de uma forma intuitiva e natural. Contudo o
processo não ocorre num contexto limitado no tempo e a critica pode surgir em
qualquer ponto do processo, já que de outra forma se correria o risco de perder
tempo em discussões espúrias ou em sugestões manifestamente irrealistas ou que
revelem desconhecimento sobre o projeto.

#### Trabalho realizado por:

* Ana Casimiro - anacasimiro1995@gmail.com
* João Bernardino - joao.mnb@gmail.com
* João Cabral - up201304395@fe.up.pt
* João Mota - up201303462@fe.up.pt

## Referências
<a name="ref1" href="http://blog.atom.io/2015/06/25/atom-1-0.html">1) Atom 1.0</a><br>
<a name="ref2" href="https://moodle.up.pt/pluginfile.php/68505/mod_resource/content/2/ESOF-Requirements%20Engineering.pdf">2) Slides da Unidade Curricular<br></a>
<a name="ref3" href="http://electron.atom.io/">3) Electron</a><br>
<a name="ref4" href="https://github.com/atom/atom/issues?q=is%3Aopen+is%3Aissue">4) Atom Issues</a><br>
<a name="ref5" href="https://github.com/jrfcabral/atom/blob/master/ESOF-docs/email1.md">5) Email de Kevin Sawicki</a>
<a name="ref6" href="http://blog.atom.io/2014/04/25/ci-for-your-packages.html">6) Travis CI for packages</a>
