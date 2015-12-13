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

No final deste projeto, os autores deste relatório consideram que o código que teve de ser desenvolvido para a implementação da *feature* acima referida foi relativamente simples, dado tratar-se de uma *feature* direcionada a um aspeto do Atom, as *panes*. Assim, foi possível estudar em tempo útil o comportamente desta componente, e efetuar alterações nos locais apropriados, não interferindo com o comportamento de outras componentes.

Em relação ao Atom, é de opinião unânime que é um projeto com potencial e bastante útil para uma edição de código prática, simples, rápida e eficaz. Para além disto e por experiência própria, os autores do presente relatório, consideram o Atom um editor de texto relativamenete pesado. Em comparação com o [*Sublime Text*](http://www.sublimetext.com/), um editor de texto semelhante, no que tocas às funcionalidade principais e essencias, é mais lento, o que se revela uma desvantagem para os utilizadores do Atom.

## Distribuição de Trabalho
* Ana Casimiro - anacasimiro1995@gmail.com
	* Contribuição: 8 horas
* João Bernardino - joao.mnb@gmail.com
	* Contribuição: 8 horas 	
* João Cabral - up201304395@fe.up.pt
	* Contribuição: 8 horas
* João Mota - up201303462@fe.up.pt
	* Contribuição: 8 horas
