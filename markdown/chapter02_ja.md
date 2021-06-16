# 第2章：道具

釈迦に説法かもしれませんが、ブラウザがHTML要素を解析するときに何が起こるか、考えてみて欲しいと思います。例えば、テキストを含んだ段落要素について考えてみましょう。p要素の開始タグと終了タグがあり、それらのあいだにテキストがあります。

	<p>テキスト</p>

この要素を見つけたブラウザは、開始タグと終了タグのあいだにあるテキストを表示します。次に、同じブラウザが認識できない要素に遭遇したとき、何が起こるかを考えてみましょう。

	<marklar>もう少し長いテキスト</marklar>

この場合も、ブラウザは開始タグと終了タグのあいだのテキストを表示します。ここで興味深いのは、ブラウザが何もしないことです。ブラウザはエラーを出しません。ブラウザは、この要素に出くわした時点でHTMLの解析を止めたり、そこから先の処理を拒否したりしません。ただ単にタグを無視して、含まれているコンテンツを表示します。

エラーに対するこのような寛大な姿勢により、HTMLの語彙は当初の21要素からHTML5の121要素へと成長していきました。HTMLに新しい要素が定義されても、古いブラウザがそれをどのように扱うか、私たちはよく知っているのです。ブラウザはタグを無視して中身を表示します。

これは非常に強力な機能です。この機能により、ブラウザはHTMLの新たな機能をそれぞれのスピードで実装することができます。すべてのブラウザが新しい要素を認識できるのを待つ必要はありません。その代わり、私たちは新しい要素をいつでも使い始めることができますし、サポートしていないブラウザがその要素で喉を詰まらせることはないと確信することができます。

	<main>どのブラウザでも表示されるであろうテキスト</main>

ブラウザがすべてのタグを同じように扱い、つまりそのコンテンツを表示するのなら、要素という語彙をHTMLで定める意味はあるでしょうか？

## マークアップの意味

HTMLの要素の中には、文字通り意味を持たないものがあります。span要素は、コンテンツについて何一つ語りません。ブラウザの処理した結果に限れば、存在しないmarklar要素を使うのと同じかもしれません。しかし、これは例外です。ほとんどのHTML要素には、存在するための理由があります。それらは、あなたや私のような制作者が遭遇する可能性のある特定の状況を考慮して定義され、かつ合意されているのです。

a要素のように、超能力を備えた特別な要素も、当然あります。a要素の場合、その超能力はhref属性に由来し、Web上のあらゆるリソースにリンクすることができます。inputやselect、textarea、buttonといった他の要素にも、それぞれに超能力があって、入力されたデータをサーバーに送信することができます。

そして、含まれるコンテンツの種類をあらわす要素があります。p要素の内容は、テキストの段落と見なされます。li要素の内容は、リストのいち項目と考えてください。ブラウザは要素の内容を、それらの意味を示唆する視覚的なヒントとともに表示します。段落は、コンテンツの前後に空白が表示されます。リストの項目では、内容の前に箇条書きのための点や数字が表示されます。

HTMLの語彙が増加し始めた当初はbigやsmall、center、font要素など、ブラウザに対して視覚的な指示を与える要素がたくさんありました。実際、視覚的な指示は、それらの要素が存在する唯一の理由であり、含んでいるコンテンツの*意味*については情報を提供しませんでした。HTMLは、意味をあらわす語彙を提供するのではなく、視覚的な指示を出すための言語になってしまう危険性があったのです。

## スタイルの問題

Håkon Wium Lieは、Tim Berners-Leeと同じ時期にCERNで働いていました。彼は、World Wide WebとHTMLの可能性にすぐ気づきました。その一方で、HTMLの意味的な能力が、視覚的な機能に埋もれてしまう危険性があることに気づいてもいました。Lieは、HTML文書の視覚的な表現を記述するための新しいフォーマットを提案しました。Cascading Style Sheets（CSS）のことです。

ほどなくオランダ人のプログラマー、Bert Bosが加わりました。二人は、デザイナーの要求に応えられるほどパワフルで、すぐに覚えられるほどシンプルな構文の開発に着手し、そして成功しました。

Web上のあらゆるサイトを思い浮かべてみてください。配色、タイポグラフィ、テクスチャー、レイアウトなど、見た目のスタイルは実にさまざまです。このような多様性を可能にしているのは、これまでに書かれたすべてのCSSをつかさどる、ただ一つのシンプルなパターンです：

	セレクタ {
		プロパティ: 値;
	}

たったこれだけです。

CSS shares HTML's forgiving attitude to errors. If a web browser encounters a selector it doesn't understand, it simply skips over whatever is between that selector's curly braces. If a browser sees a property or a value it doesn't understand, it just ignores that particular declaration. The browser does not throw an error. The browser does not stop parsing the CSS at this point, refusing to go any further.

	marklar {
		marklar: marklar;
	}

Just as with HTML, this loose error-handling has allowed CSS to grow over time. New selectors, new properties, and new values have been added to the language's vocabulary over the years. Whenever a new feature lands in CSS, designers and developers know that they can safely use it, even if it isn't yet widely supported in browsers. They can rest assured that old browsers will react to new features with complete indifference.

Just because a language is elegant and well-designed doesn't mean that people will use it. CSS arrived later than HTML. Designers didn't spend the intervening years waiting patiently for a way to style their documents on the web. They used what was available to them.

###Killing it

In 1996 David Siegel published a book entitled _Creating Killer Websites_. In it, he outlined a series of ingenious techniques for wrangling eye-catching designs out of the raw material of HTML.

One technique involved using a transparent GIF, just one pixel by one pixel in size. If this was inserted into a page as an IMG element, but given precise values in its <code>width</code> and <code>height</code> attributes, designers could control the amount of whitespace in their designs.

Another technique used the TABLE element. This element—along with its children TR and TD—was intended to describe tabular data. But with the right values applied to the widths and heights of table cells, it could be used to recreate just about any desired layout.

These were hacks; clever solutions to tricky problems. But they had unfortunate consequences. Designers were treating HTML as a tool for the appearance of content instead of a language for describing the meaning of content. CSS was a solution to this problem, if only designers could be convinced to use it.

###ブラウザ戦争

WebデザイナーがCSSを使わなかった理由のひとつに、ブラウザのサポート不足がありました。かつて2つのメジャーなブラウザが、Webの主導権を争っていました。Microsoft Internet ExplorerとNetscape Navigatorです。両者はデザイン的に相容れない存在でした。一方のブラウザが、新しい要素や属性を作ったとします。するともう一方のブラウザは、まったく同じ目的において、異なる独自の要素や属性を作ったのです。

Perhaps the thinking behind this strategy was that web designers would have to choose which proprietary features they were going to get behind, like children being forced to choose between parents. In reality web designers had little choice but to write for both browsers which meant doing the twice the work.

A group of web designers decided enough was enough. They gathered together under the banner of the Web Standards Project and began lobbying Microsoft and Netscape to abandon their proprietary ways and adopt standards such as CSS.

The tide began to turn with the launch of Internet Explorer 5 for the Mac, a browser that shipped with impressive CSS support. If this was the future of web design, life was about to get a lot more productive and creative.

Some forward-thinking web designers caught the CSS bug early. They redesigned their websites using CSS for layout instead of using TABLEs and spacer GIFs. True to the founding spirit of the web, they shared what they were learning and encouraged others to make the switch to CSS.

Perhaps the best demonstration of the power of CSS was a website called the CSS Zen Garden, created by Dave Shea. It was a showcase of beautiful and varied designs, all of them accomplished with CSS. Crucially, the HTML remained the same.

Seeing the same HTML document styled in a multitude of different ways drove home one of the beneficial effects of CSS: separation of concerns.

###Coupling

In any system, from urban infrastructure to a computer programme, the designers of that system can choose the degree to which the pieces of the system depend on one another. In a tightly-coupled system, every piece depends on every piece. In a loosely-coupled system, all the pieces are independent, with little to no knowledge of the other pieces.

In a tightly-coupled system, each part of the system can make assumptions about the other parts. These systems can be designed quite quickly, but at a price. They lack resilience. If one piece fails, it could take the whole system with it.

Designing a loosely-coupled system can take more work. The payoff is that the overall result is more resilient to failure. Individual parts of the system can be swapped out with a minimum of knock-on effects.

The hacks pioneered by David Siegel tightly coupled structure and presentation into a single monolithic HTML file. The adoption of CSS eased this dependency, bringing the web closer to the modular approach of the UNIX philosophy. The presentational information could be moved into a separate file: a style sheet. That's how a single HTML document at the CSS Zen Garden could have so many different designs applied to it.

The style sheet still needs to have some knowledge of the HTML document's structure. Quite often, "hooks" are added into the markup to make it easier to style: specific values of <code>class</code> or <code>id</code> attributes, for example. So HTML and CSS aren't completely decoupled. They form a partnership but they also have an arrangement. The markup document might decide that it wants to try seeing other style sheets sometimes. Meanwhile, the style sheet could potentially be applied to other documents. They are loosely coupled.

##Dancing about architecture

It takes time for a discipline to develop its own design values. Web design is a young discipline indeed. While we slowly begin to form our own set of guiding principles, we can look to other disciplines for inspiration.

The world of architecture has accrued its own set of design values over the years. One of those values is the principle of material honesty. One material should not be used a substitute for another. Otherwise the end result is deceptive.

Using TABLEs for layout is materially dishonest. The TABLE element is intended for marking up the structure of tabular data. The end result of using TABLEs, FONT elements, and spacer GIFs is a façade. At first glance everything looks fine, but it won't stand up to scrutiny. As soon as such a website is stress-tested by actual usage across a range of browsers, the façade crumbles.

Using CSS for presentation is materially honest—that's the intended use of CSS. It also allows HTML to be materially honest. Instead of trying to fulfil two roles—structure and presentation—HTML can return to fulfilling its true purpose, marking up the meaning of content.

It's still possible to use (or abuse) CSS to be materially dishonest. For the longest time, there was no easy way to add rounded corners to an element using CSS. Instead, web designers found ways to hack around the problem, putting background images on the element to simulate the same end effect. It worked up to a point, but just like the spacer GIF hack, it was a façade. Then the <code>border-radius</code> property arrived. Now designers can have their rounded corners in a materially honest way.

Crucially, designers were able to use new properties like <code>border-radius</code> long before every web browser supported them. That's all thanks to the liberal error-handling model of CSS. Newer browsers would display the rounded corners. Older browsers would not throw an error. Older browsers would not stop parsing the CSS and refuse to parse any further. They would simply ignore the instructions they didn't understand and move on. No harm, no foul.

Of course this means that the resulting website will look different in different browsers. Some people will see rounded corners. Others won't.

And that's okay.
