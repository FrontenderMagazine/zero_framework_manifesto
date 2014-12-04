Перестаньте писать Javascript фреймворки.

Javascript фреймворки подобно смерти и налогам; неминуемые и неизбежны. Я 
уверен, что если бы я мог быть мухой на той стене, где каждый раз, когда кто-то
начинает новый веб-проект, то самый первый вопрос, который они бы задали ето, 
какой JS фреймворк мы используем? Вот как укоренилось роль JS фреймворков в 
отрасли сегодня. Но это не тот путь, по которому должно все идти, и на самом 
деле, ето нужно остановить.

> Angular и Backbone и Ember, о мой.

В течение долгого времени [веб-платформы][1], технологичный стек наиболее 
лаконично описывается как HTML+CSS+JS, был, из-за отсутствия лучшего термина,
катастрофичным. Кто может забыть блочную модель IE, или layer тег? Я уверен, 
что у некоторых из вас началось подергивание из-за воспоминаний о старых плохих
временах веб-разработки благодаря словам выше.

Долгое время было намного несоответствия между браузерами и мы, как отрасль, 
должны были писать фреймворки как обои над ними. Проблема в том,
что разногласия даже по фундаментальных вопросах, среди браузеров, например как 
события распространяются или какие теги поддерживаются, так что каждый фреймворк
не только был обоями над дирами, но разработывал свои собственные модели, как 
браузер должен работь. На самом деле их собственные модел*и*, во множественном 
числе, потому что вы должны изобрести модель о том как события распространяются,
модель как взаимодействовать с DOM, и т.д. Много изобретений было сделано. И так 
фреймворки были написаны, каждый как снежинка, тысячи цветков цвели  и дали нам 
что то вроде JQuery и Dojo и MochiKit и Ext JS и AngularJS и Backbone и Ember и 
React. За прошедшие *десять* лет мы наблюдали устойчивый парад JS фреймворков.

Но что-то еще произошло за последние десять лет; браузеры стали лучше.
Их поддержка стандартов улучшилась, и сейчас есть вечнозеленые браузеры:
автоматическое обновление браузеров, каждая версия более способна и стандарто
совместима, чем в прошлом. В новых стандартах, таких как:

*   [HTML Imports][2]
*   [Object.observe][3]
*   [Promises][4]
*   [HTML Templates][5]

Я думаю, пришло время переосмыслить модель JS фреймворков. Нет необходимости
изобретать еще один способ сделать что-то, просто используйте HTML+CSS+JS.

Так почему же мы все еще пишем JS фреймворки? Я думаю, что большая часть сего
инерция, это привычка. Но так ли это плохо, это не так, как фреймворки активно
вредно, не так ли? Но, давайте сначала определим то, что я имею в виду под веб
фреймворком. На самом деле ето градиент кода, который начинается с простого 
фрагмента, например Gist, и потом движется ко все более крупной коллекции кода,
двигаясь вверх к библиотеке, и, наконец, фреймворку:

> gist -> library -> framework 

Фреймворки не только крупные библиотеки, они имеют свои собственные модели для 
того, как взаимодействовать с событиями, с DOM, и т.д. Так почему избегать 
фреймворков?

**Абстракции** Ну, одна из проблем фреймворков, как правило, одина из
их торговых точок, ето то что они абстрагируються от платформы, так что вы 
можете сосредоточиться на создании собственного программного обеспечения. 
Проблема в том, что теперь вам нужно знать две системы, HTML+CSS+JS и фреймворк.
Конечно, если фреймворк был бы идеально абстрагирован от сети как платформы, 
за которую вы никогда не должны выходить, но догадайтесь, что, 
[утечка абстракции][6]. Таким образом, вы должны знать, HTML+CSS+JS, потому что
в какой-то момент ваша программа не будет работать так, как вы ожидаете, и вы 
будете копаться вниз через все слои в фреймворке, что бы понять что не так,
вплоть до HTML+CSS+JS.

> Картографирование айсберга. 

Фреймворк, как айсберг, те 10% плавающей над водой не выглядят опасно, зато 
скрытые 90%, именно то, что в конечном счете ловит вас. На самом деле это даже
более склонны, изучение фреймворка, как картографировать айсберг, для того, чтобы
использовать его вам нужно узнать все о нем, применить усилие картографировать
всей особености, и в конечном счете процесс идет в никуда, потому что
айсберг будет таять в любом случае.

**Виджеты** Другой пункт продажи фреймворков, то что вы можете получить доступ к
библиотека виджетов. Но на самом деле, вы не должны принимать фреймворки, чтобы 
получить доступ к виджетам, все они должны быть ортогональны и независимы. 
Хорошим примером этого на сегодня есть [CodeMirror][7], редактор подсветки 
синтаксиса кода, построенного на JavaScript. Вы можете использовать его в везде,
никаких фреймворков не требуется.

Ето также утеряные усилия в создании виджетов для фреймворка. Помните все те 
виджеты которые вы написали для MochiKit? Да, как много хорошего они делают для 
вас сейчас когда вы мигрировали на Ember, или Angular?

**Привязка данных** Честно говоря, я никогда не нуждался в этом, но если вам 
нужно, тогда это должно быть в виде библиотеки, а не фреймворка.

Долгосрочная проблема с фреймворками, что они в конечном итоге заканчивают как 
силос, они сегментят пейзаж, виджет построенный для фреймворка А не работает в Б.
Это потеряные усилия.

Итак, как выглядит пост-фреймворковый мир?

> HTML+CSS+JS есть мой фреймворк. 

The fundamental idea is that frameworks aren't needed, use the capabilities
already built into HTML+CSS+JS to build your widgets. Break apart the monoliths 
into orthogonal components that can be mixed in any combination. The final 
pieces that enable all of this fall under the umbrella of[Web Components][8]

HTML Imports, HTML Templates, Custom Elements, and Shadow DOM are the enabling
technologies that should allow us to cut the cord from frameworks, allowing the 
creation of reusable elements and functionality. For a much better introduction 
see these articles and libraries:

*   [HTML Imports][9]
*   [Polymer][10]
*   [X-Tag][11]
*   [Bosonic][12]

So, we all create [<x-flipbox>][13]'s, declare victory, and go home? 

No, not actually, the first thing you need for working with Web Components are
polyfills for that functionality, such as X-Tag and Polymer. The need for those 
will decrease over time as browsers flesh out their implementations of those 
specifications.

A point to be stressed here is that these polyfills aren't frameworks that
introduce their own models to developing on the web, they enable the HTML 5 
model. But that isn't really the only need, there are still minor gaps in the 
platform where one browser deviates in a small way from current standards, and 
that's something we need to polyfill.[MDN][14] seems to have much of the needed
code, as the documentation frequently contains
[ short per-function polyfills][15].

So one huge HTML 5 Polyfill library would be good, but even better would be
what I callhtml-5-polyfill-o-matic, a set of tools that allows me to write Web
Components via bog standard HTML+JS and then after analyzing my code, either via
static analysis or via`Object.observe` at runtime, it produces a precise subset
of the full HTML 5 polyfill for my project.

This sort of functionality will be even more important as I start trying to mix
and match web components and libraries from multiple sources, i.e. an <x-foo> 
from X-Tag and a <core-bar> from Polymer, does that mean I should have to 
include both of their polyfill libraries?
([It turns out the answer is no][16].) And how exactly should I get these
custom elements? Both X-Tag and Brick have custom bundle generators:

*   [Brick Download][17] 
*   [X-Tag Download][18] 

If I start creating custom elements do I need to create my own custom bundler
too? I don't think that's a scalable idea, I believe we need idioms and tools 
that handle this much better. This may actually mean changing how we do open 
source; a 'widget' isn't a project, so our handling of these things needs to 
change. Sure, still put the code in Git, but do you need the full overhead of a 
GitHub project? Something lighter weight, closer to a Gist than a current 
project might be a better fit. How do I minimize
/[vulcanize][19] all of this code into the right form for use in my project?
Something like[Asset Graph][20] might be a good start on that. 

So what do we need now? 

That's what we need to build a future where we don't need to learn the latest
model of the newest framework, instead we just work directly with the platform, 
pulling in custom elements and libraries to fill specific needs, and spend our 
time building applications, not mapping icebergs.

## Q&A {#qa}

**Q:** Why do you hate framework authors.

**A:** I don’t hate them. Some of my best friends are framework authors. I
will admit a bit of inspiration from the tongue-in-cheek
[you have ruined javascript][21], but again, no derision intended for framework
authors.

**Q:** You can’t do \__\_|\_ in HTML5, for that you need a framework.

**A:** First, that's not a question. Second, thanks for pointing that out. Now
let's work together to add the capabilities to HTML 5 that allows \__\_|\_ to be
done w/o a framework.

**Q:** But \___| isn't a framework, it's a library!

**A:** Yeah, like I said, it’s a gradient from gist to framework, and you
might draw the lines slightly differently from me. That's OK, this isn't about 
the categorization of any one particular piece of software, it's about moving 
away from frameworks.

**Q:** I've been doing this for years, with \_\_\_| and \\_\_\_| and \\___|.

**A:** Again, that's not a question, but regardless, good for you, you should
be in good shape to help everyone else.

**Q:** So everyone needs to rewrite dropdown menus, tabs, sliders and toggles
themselves?

**A:** Absolutely not, the point is there should be a way to create those
elements in a way that doesn't require buying into one particular framework.

**Q:** Dude, all those HTML Imports are going to kill my sites performance.

**A:** Yes, if you implemented all this stuff naively it would, which is why I
[mentioned the need for tools][22] to compile and crush all the HTML, CSS, and
JS.

**Q:** So I'm not supposed to use *any* libraries? 

**A:** No, that's not what I said, I was very careful to delineate a line
between libraries and frameworks, a library providing an orthogonal piece of 
functionality that can be used with other libraries. Libraries are fine, it's 
the frameworks that demand 100% buyin that I'd like to see us move away from.

**Q:** Но мне нравится привязки данных!

**A:** Много кто ето делает, я только высказываю личные предпочтения. Я не 
говорю, что *вы* не должны использовать связывание данных, но только то, что вам
не нужно, принимать весь фреймворк, чтобы получить привязку данных, есть 
автономные библиотеки для етого.

2014-05-09

 [1]: http://platform.html5.org/
 [2]: http://w3c.github.io/webcomponents/spec/imports/
 [3]: http://wiki.ecmascript.org/doku.php?id=harmony:observe
 [4]: http://www.html5rocks.com/en/tutorials/es6/promises/
 [5]: http://www.w3.org/TR/html5/scripting-1.html#the-template-element
 [6]: http://www.joelonsoftware.com/articles/LeakyAbstractions.html
 [7]: http://codemirror.net/
 [8]: http://www.w3.org/TR/components-intro/
 [9]: http://www.html5rocks.com/en/tutorials/webcomponents/imports/
 [10]: http://www.polymer-project.org/
 [11]: http://www.x-tags.org/
 [12]: http://bosonic.github.io/
 [13]: http://mozbrick.github.io/docs/brick-flipbox.html
 [14]: https://developer.mozilla.org
 [15]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind#Compatibility
 [16]: http://www.polymer-project.org/articles/polymer-xtag-vanilla.html
 [17]: http://mozilla.github.io/brick/download.html
 [18]: http://www.x-tags.org/download
 [19]: https://github.com/Polymer/vulcanize
 [20]: https://github.com/assetgraph/assetgraph-builder
 [21]: http://codeofrob.com/entries/you-have-ruined-javascript.html
 [22]: http://bitworking.org/news/2014/05/zero_framework_manifesto#tools2
