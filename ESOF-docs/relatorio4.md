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

Ao nível intermédio são ainda de salientar as capacidades de análise de comportamento fornecidas pelo *Jasmine*. A *framework* permite que sejam definidos um conjunto de *spies* a operar sobre métodos de objetos, que permitem extrair informação detalhada sobre a forma como os mesmos estão a ser chamados dentro do código. Fica assim possibilitado um controlo de granularidade bastante fina não só das entradas e saídas de cada objeto ao nível do teste unitário, mas também do seu comportamento interno. Por exemplo é possível definir um *spy* que regista as chamadas efetuadas a uma função, e mais tarde é possível fazer o teste falhar se essa não tiver sido chamada no decorrer do teste.


Outro tipo de testes que são frequentemente utilizados são os de integração. Este tipo de testes incide principalmente sobre as interfaces utilizadas e sobre a articulação inter-componente. Neste contexto cabe realçar as facilidades de comunicação fornecidas pela plataforma *Electron* sobre a qual o *Atom* está construído. Esta plataforma define de forma clara uma separação em dois componentes de todo o *software* que sobre ela se construa, como já foi discutido em profundidade no relatório 3. O *Electron* define também as interfaces de comunicação entre componentes que podem ser utilizadas. Sendo todas estas interfaces de comunicação genéricas, é sobre elas que deve, em princípio, ser construído um protocolo de comunicação especifico da aplicação a desenvolver. Torna-se assim possível controlar, pela invocação dos métodos de comunicação fornecidos, o comportamento do sistema, manipulando a forma de integração inter-componente.

#### Observabilidade dos resultados dos testes
Os testes do *Atom* são corridos sobre uma plataforma tecnológica baseada numa *framework* de
definição de especificações para *JavaScript* denominada *Jasmine*. A *framework* usada dispõe de uma *GUI* integrada no próprio Atom que permite analisar detalhadamente o resultado de cada teste. Em caso de falha é possível extrair informação relativa à asserção que falhou com facilidade.


A natureza distribuída dos projetos *open-source*, parece, na opinião dos autores do presente relatório, exigir que seja garantida não só a observabilidade dos resultados dos testes corridos sobre as alterações efetuadas por cada programador, como também que seja possível analisar os resultados dos teste corridos sobre código desenvolvido por terceiros e que não esteja ainda integrado na base de código do projeto. Para este fim o *Atom* recorre à plataforma de testes *Travis CI*, que possibilita a integração da interface de *pull requests* com a *suite* de testes, sendo os resultados visiveis na página correspondente ao *pull request*.

#### Isolabilidade
A isolabilidade das diferentes componentes do Atom varia consoante o caso. Existem componentes que funcionam por cima de outras, como por exemplo no caso da classe *TextEditor*, cujo método de inicialização exige uma instância da classe *Workspace*. A sua testabilidade individual ao nível dos testes unitários fica assim comprometida, pois não mais se pode considerar que está a ser seguido um modelo *black box* onde alterações exteriores podem influenciar de forma não controlável o resultado dos teste, devido a variações, à partida não previsiveis, dos dados de *input* no sistema em teste.

Para permitir evitar este problema o Atom recorre à facilidades de isolação fornecidas pela framework de testes *Jasmine* utilizada. São disponibilizados um conjunto de funções que operam sobre métodos de um objeto que permitem controlar o seu comportamento. Em concreto é possível efetuar a substituição do valor de retorno do método por um pré-determinado no contexto do teste, provocar o lançamento de erros quando um método for chamado, mesmo que em circunstâncias normais esse erro não fosse causado, ou mesmo substituir a invocação do método por outro.

Estas facilidades permitem a definição de *mocks* que garantem que cada objeto pode, com a devida diligência, ser completamente isolado do seu contexto.

#### Separação das responsabilidades de cada componentes
A arquitetura do Atom é, como já foi referido, baseada em classes. É da opinião do grupo que cada classe tem um trabalho bastante bem definido.

#### Documentação dos componentes
O Atom está [bem documentado](https://atom.io/docs/api/v1.2.3/AtomEnvironment), em parte devido à sua natureza *open-source*, que obriga a que a documentação seja explícita e concisa para que possa ser consultada e aprendida celeremente e compreendida pelo maior número de pessoas possível.

#### Heterogeneidade
No repositório do Atom está disponível uma bateria de testes de tamanho considerável. Estes testes são na sua maioria testes unitários, havendo também um número razoável de testes de integração. Além disso, o Atom vem [equipado com funcionaliades que lhe permitem correr esses testes dentro de si mesmo.](<eu gostava munto munto d ter aqui um link pras instruçoes d correr os testes mas num encontro :(>)

### Estatísticas dos Testes
Como já foi mencionado, o Atom disponibiliza uma bateria de testes no seu repositório. Os mesmo estão separados por vários ficheiros, conforme a classe sobre a qual incidem. Presentemente parecem existir 1850 testes unitários distintos, bem como alguns testes de integração. O Atom fornece ainda scripts que permitem correr estes testes de várias formas, incluindo suporto para Travis CI e, mais recentemente, AppVeyor CI.
