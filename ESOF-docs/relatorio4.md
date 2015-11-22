# [ESOF] Relatório 4 - Verificação e Validação

Este é o quarto relatório dedicado à análise dos processos de engenharia de software empregues pelo projeto *open-source* Atom. Desta feita serão analisados os processos de verificação e validação
empregues pela equipa no desenvolvimento da aplicação. Em primeiro lugar serão discutidas as caracteristicas lógicas e organizacionais do código e da tecnologia de especificação de testes utilizada. Procura-se entender de que forma é que a base de código de aplicação se ajusta e enquadra no contexto da execução de testes unitários e de integração e tambem quais as valências da plataforma de testes utilizada que permite ultrapassar os principais desafios que se lhe colocam, nomeadamente o da isolação de componentes e a controlabilidade dos testes sobre o seu comportamento.

## Bug Reports, Testes e Revisão de Código

### Grau de Testabilidade
No toca à testabilidade, o Atom aparenta estar bem estruturado. A arquitetura do programa, baseada em pacotes e classes, introduz uma modularidade que torna simples a eficaz separação dos testes a correr, enquanto que a sua base, o electron, permite que haja coesão e comunicação entre os diferentes componentes, podendo assim testar-se também aspetos de comunicação em diferentes módulos com facilidade.

Nas subsecções seguintes serão analisados em maior detalhe os vários aspetos que permitem avaliar as caracteristicas de testabilidade.


#### Controlabilidade dos componentes em estudo
O Atom apresenta uma organização de código e um paradigma de programação orientado ao objecto, recorrendo às capacidades que o *javascript* confere nesta área. A linguagem de programação utilizada
fornece as ferramentas adequadas para permitir manipular de forma completa e controlada tanto o comportamento dos objetos instanciados como o valor dos dados neles guardados. Os testes unitários são  tendencialmente orientados ao estudo do comportamento de cada classe e objeto em particular, sendo o seu contexto abstraído com recurso a várias técnicas, que se discutirão em maior profundidade na secção sobre Isolabilidade. É portanto possível compreender que as caracteristicas de controlabilidade dos componentes do Atom se ajustam particularmente bem à realização de testes unitários.

Outro tipo de testes que são frequentemente utilizados são os de integração. Este tipo de testes incide principalmente sobre as interfaces utilizadas e sobre a articulação inter-componente. Neste contexto cabe realçar as facilidades de comunicação fornecidas pela plataforma *Electron* sobre a qual o *Atom* está construído. Esta plataforma define de forma clara uma separação em dois componentes de todo o *software* que sobre ela se construa, como já foi discutido em profundidade no relatório 3. O *Electron* define também as interfaces de comunicação entre componentes que podem ser utilizadas. Sendo todas estas interfaces de comunicação genéricas, é sobre elas que deve, em princípio, ser construído um protocolo de comunicação especifico da aplicação a desenvolver. Torna-se assim possível controlar, pela invocação dos métodos de comunicação fornecidos, o comportamento do sistema, manipulando a forma de integração inter-componente.

#### Observabilidade dos resultados dos testes
Os testes implementados no Atom vêem equipados com métodos que permitem a observação do estado e comportamento dos diferentes componentes, bem como métodos que avaliam a correção dos mesmos.

#### Isolabilidade
A isolabilidade das diferentes componentes do Atom varia consoante o caso. Existem componentes que funcionam por cima de outras, como por exemplo no caso da classe *TextEditor*, cujo método de inicialização exige uma instância da classe *Workspace*. Assim sendo, ainda que a influência dos componentes que estão presentes e não estão em teste seja mínima, é verdade que isto causa problemas em termos de isolabilidade.

#### Separação das responsabilidades de cada componentes
A arquitetura do Atom é, como já foi referido, baseada em classes. É da opinião do grupo que cada classe tem um trabalho bastante bem definido.

#### Documentação dos componentes
O Atom está [bem documentado](https://atom.io/docs/api/v1.2.3/AtomEnvironment), em parte devido à sua natureza *open-source*, que obriga a que a documentação seja explícita e concisa para que possa ser consultada e aprendida celeremente e compreendida pelo maior número de pessoas possível.

#### Heterogeneidade
No repositório do Atom está disponível uma bateria de testes de tamanho considerável. Estes testes são na sua maioria testes unitários, havendo também um número razoável de testes de integração. Além disso, o Atom vem [equipado com funcionaliades que lhe permitem correr esses testes dentro de si mesmo.](<eu gostava munto munto d ter aqui um link pras instruçoes d correr os testes mas num encontro :(>)

### Estatísticas dos Testes
Como já foi mencionado, o Atom disponibiliza uma bateria de testes no seu repositório. Os mesmo estão separados por vários ficheiros, conforme a classe sobre a qual incidem. Presentemente parecem existir 1850 testes unitários distintos, bem como alguns testes de integração. O Atom fornece ainda scripts que permitem correr estes testes de várias formas, incluindo suporto para Travis CI e, mais recentemente, AppVeyor CI.
