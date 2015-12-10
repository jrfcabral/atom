# [ESOF] Relatório 5 - Evolução de software

Neste relatório é exposto o processo pelo qual passaram os constintuíntes do grupo de forma a identificar e evoluir uma feature do Atom.

## Identificação de uma feature

O Atom possui, além da sua página de github, onde alguns issues representam sugestões de funcionalidades a implementar, um blog, no qual está integrado um fórum onde são discutidos variados aspetos, de entre os quais novas funcionalidades. Foi neste fórum que encontramos uma feature que consideramos ser acessível em termos de dificuldade tendo em conta o tempo disponível para a concretização do presente trabalho.

<se alguém encontrasse o link pra feature era top, brigado>
<em alternativa uma descrição da feature a desenvolver er aporreiro, eu posso fazer se n encontrarmos até ao fim da aula>


## Identificação de componentes que implementam a feature

Após alguma pesquisa, constatou-se que a maneira como o Atom trata o fechar de tabs varia conforme o comando dado. O atom dispões de uma série de comandos, de entre os quais alguns tratam do fecho de tabs, seja individualmente ou em grupo. Alguns destes comandos podem ser encontrados no ficheiro [register-default-commands.coffee](https://github.com/atom/atom/blob/master/src/register-default-commands.coffee#L72). Pelo facto de as *tabs* implementadas em atom fazerem parte de um package (aparentemente não do core?), foi decidido a funcionalidade a evoluir, em concreto, seria o comando pane:close, mostrado no ficheiro acima. Foi também decidido que a melhor (e mais simples) maneira de implementar a feature pretendida seria acrescentar dois botões, nomeadamente o botão *"No For All"* e o *"Yes For All"*. Ao serem pressionados, a função que lança a janela de opções de gravação retorna valores específicos, que serão apanhados na função que a chama (destroyItem). Esta função, por sua vez, retornará também um código indicativo da opção selecionada, fazendo com que, na função onde está a ser corrido o ciclo que itera sobre os *items* de uma pane passe para um ramo diferente onde, simplesmente ignorará a função destroyItem, executando diretamente a função pretendida.

<imagens, clarificaçoes, etc, etc>

## Submissão da feature desenvolvida

AINDA N FIZEMOS
