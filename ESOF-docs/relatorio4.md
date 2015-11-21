# [ESOF] Relatório 4 - Verificação e Validação
## Bug Reports, Testes e Revisão de Código

### Grau de Testabilidade

No toca à testabilidade, o Atom aparenta estar extremamente bem estruturado. A arquitetura do programa, baseada em pacotes e classes, introduz uma modularidade que torna simples a eficaz separação dos testes a correr, enquanto que a sua base, o electron, permite que haja coesão e comunicação entre os diferentes componentes, podendo assim testar-se também aspetos multi-modulares com relativa facilidade (testes de integração).

#### Controlabilidade dos componentes em estudo
A manipulação do estado dos componentes a testar no Atom é, no geral, conseguida com elevada facilidade, recorrendo a métodos disponíveis nos mesmos.

#### Observabilidade dos resultados dos testes
Os testes implementados no Atom vêem equipados com métodos que permitem a observação do estado e comportamento dos diferentes componentes, bem como métodos que avaliam a correção dos mesmos.

#### Isolabilidade
A isolabilidade das diferentes componentes do Atom varia consoante o caso. Existem componentes que funcionam por cima de outras, como por exemplo no caso da classe *TextEditor*, cujo método de inicialização exige uma instância da classe *Workspace*. Assim sendo, ainda que a influência dos componentes que estão presentes e não estão em teste seja mínima, é verdade que isto causa problemas em termos de isolabilidade.

#### Separação das responsabilidades de cada componentes
A arquitetura do Atom é, como já foi referido, baseada em classes. É da opinião do grupo que cada classe tem um trabalho bastante bem definido.

#### Documentação dos componentes
O Atom está [extremamente bem documentado](https://atom.io/docs/api/v1.2.3/AtomEnvironment), em parte devido à sua natureza *open-source*, que obriga a que a documentação seja explícita e concisa para que possa ser consultada e aprendida celeremente e compreendida pelo maior número de pessoas possível.

#### Heterogeneidade
No repositório do Atom está disponível uma bateria de testes de tamanho considerável. Estes testes são na sua maioria testes unitários, havendo também um número razoável de testes de integração. Além disso, o Atom vem [equipado com funcionaliades que lhe permitem correr esses testes dentro de si mesmo.](<eu gostava munto munto d ter aqui um link pras instruçoes d correr os testes mas num encontro :(>)

### Estatísticas dos Testes
Como já foi mencionado, o Atom disponibiliza uma bateria de testes no seu repositório. Os mesmo estão separados por vários ficheiros, conforme a classe sobre a qual incidem. Presentemente parecem existir 1850 testes unitários distintos, bem como alguns testes de integração. O Atom fornece ainda scripts que permitem correr estes testes de várias formas, incluindo suporto para Travis CI e, mais recentemente, AppVeyor CI.
