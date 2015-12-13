# [ESOF] Relatório 5 - Evolução de software

De forma a evoluir uma *feature* do Atom, este relatório expõe o processo realizado na implementação de uma nova funcionalidade desenvolvida pelos autores deste relatório.

## Identificação de uma *feature*

O Atom possui, além da sua página de [github](https://github.com/atom), onde alguns *issues* representam sugestões de funcionalidades a implementar, um [blog](https://atom.io/), no qual está integrado um [fórum](https://discuss.atom.io/) onde são discutidos variados aspetos, de entre os quais novas funcionalidades a serem implementadas. Foi nos *issues* do repositório que encontramos uma [feature](https://github.com/atom/atom/issues/9957) que nos pareceu acessível em termos de complexidade, dado o tempo disponível, e bastante oportuna.


## Identificação de componentes que implementam a *feature*

Após alguma pesquisa, constatou-se que a maneira como o Atom trata o fechar de *tabs* varia conforme o comando dado. O Atom dispõe de uma série de comandos, de entre os quais alguns tratam do fecho de *tabs*, seja individualmente ou em grupo. Alguns destes comandos podem ser encontrados no ficheiro [register-default-commands.coffee](https://github.com/atom/atom/blob/master/src/register-default-commands.coffee#L72). Pelo facto de as *tabs* implementadas no Atom fazerem parte de um [package](https://github.com/atom/tabs), foi decidido que a funcionalidade a evoluir, em concreto, seria o comando **pane:close**, mostrado no ficheiro acima. Foi também decidido que a melhor maneira de implementar a *feature* pretendida seria acrescentar dois botões, nomeadamente o botão *"No For All"* e o *"Yes For All"* :
```javascript
 buttons: if multiple then ["Save", "Cancel", "Don't Save", "No For All", "Yes For All"] else ["Save", "Cancel", "Don't Save"]
```

Ao serem pressionados, a função que lança a janela de opções de gravação retorna valores específicos, que serão apanhados na função que a chama **confirmClose**. Esta função, que itera sobre os *items* pertencentes a uma *pane*, terá comportamentos distintos consoante o valor que lhe é passada.

## Submissão da feature desenvolvida

O [pull request](https://github.com/atom/atom/pull/10034) foi submetido pelos autores do presente relatório, pendendo a aprovação do *staff* encarregue do Atom.

## Análise Crítica

É da opinião dos autores do presente relatorio que o desenvolvimento do código para a implementação da *feature* acima referida foi relativamente simples, dado tratar-se de uma *feature* cujo foco é apenas um componente do Atom, as *panes*. Assim, foi possível estudar em tempo útil o comportamente deste componente e efetuar alterações nos locais apropriados, não interferindo com o comportamento de outras componentes.

Chegado o final da série de trabalhos desenvolvidos no âmbito da cadeira de Engenharia de Software é dado aqui um balanço final relativamento ao software que tem vindo a ser estudado pelos autores deste relatório, o Atom. É de opinião unânime que este é um projeto com potencial e bastante útil para uma edição de código prática, simples, rápida e eficaz. A sua modularidade permite uma mais fácil integração de funcionalidades desenvolvidas posteriormente, algo que é beneficial num projeto *open-source*. O Atom é, no entanto, por experiência própria, um editor de texto relativamenete pesado, no sentido em que a sua performance pode, por vezes, deixar algo a desejar. Além disso, trata-se de um projeto que, talvez parcialmente devido à sua natureza aberta, não é completamente estável e não está completamente isento de *bugs*.

## Distribuição de Trabalho
* Ana Casimiro - anacasimiro1995@gmail.com
	* Contribuição: 8 horas
* João Bernardino - joao.mnb@gmail.com
	* Contribuição: 8 horas 	
* João Cabral - up201304395@fe.up.pt
	* Contribuição: 8 horas
* João Mota - up201303462@fe.up.pt
	* Contribuição: 8 horas
