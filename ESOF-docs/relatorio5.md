# [ESOF] Relatório 5 - Evolução de software

Neste relatório é exposto o processo pelo qual passaram os constintuíntes do grupo de forma a identificar e evoluir uma feature do Atom.

## Identificação de uma feature

O Atom possui, além da sua página de github, onde alguns issues representam sugestões de funcionalidades a implementar, um [blog](https://atom.io/), no qual está integrado um [fórum](https://discuss.atom.io/) onde são discutidos variados aspetos, de entre os quais novas funcionalidades. Foi nos issues do repositório que encontramos uma [feature](https://github.com/atom/atom/issues/9957) que nos pareceu acessível em termos de complexidade dado o tempo disponível.


## Identificação de componentes que implementam a feature

Após alguma pesquisa, constatou-se que a maneira como o Atom trata o fechar de tabs varia conforme o comando dado. O Atom dispões de uma série de comandos, de entre os quais alguns tratam do fecho de tabs, seja individualmente ou em grupo. Alguns destes comandos podem ser encontrados no ficheiro [register-default-commands.coffee](https://github.com/atom/atom/blob/master/src/register-default-commands.coffee#L72). Pelo facto de as *tabs* implementadas em atom fazerem parte de um package (aparentemente não do core?), foi decidido que a funcionalidade a evoluir, em concreto, seria o comando pane:close, mostrado no ficheiro acima. Foi também decidido que a melhor (e mais simples) maneira de implementar a feature pretendida seria acrescentar dois botões, nomeadamente o botão *"No For All"* e o *"Yes For All"*. Ao serem pressionados, a função que lança a janela de opções de gravação retorna valores específicos, que serão apanhados na função que a chama (confirmClose). Esta função, que itera sobre os *items* pertencentes a uma pane, terá comportamentos distintos consoante o valor que lhe é passada.

## Submissão da feature desenvolvida

O [pull request](https://github.com/atom/atom/pull/10034) foi submetido pelos autores do presente relatório, pendendo a aprovação do *staff* encarregue do Atom.
