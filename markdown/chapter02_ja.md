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

CSSはHTMLと同様、エラーに寛容です。Webブラウザが理解できないセレクタに遭遇した場合、そのセレクタの中括弧のあいだにある中身を単純にスキップします。ブラウザは、理解できないプロパティや値があっても、その宣言を無視します。ブラウザはエラーを出力しません。その時点でCSSの解析を止め、以降の処理を拒否するようなことは無いのです。

	marklar {
		marklar: marklar;
	}

HTMLと同様、この緩いエラー処理のおかげで、CSSは時がたつにつれ成長してきました。新しいセレクタ、新しいプロパティ、そして新しい値が、長年にわたり語彙に追加されてきました。CSSに新しい機能が追加されるたびに、デザイナーや開発者は、それがまだブラウザで広くサポートされていなくても、安全に使用できることを知っています。古いブラウザは新機能にはまったく無反応ですから、安心です。

エレガントで適切に設計された言語だからといって、人々がそれを使うとは限りません。CSSはHTMLよりも後になって登場しました。それまでのあいだ、デザイナーはWeb上の文書にスタイル付けする方法をじっと待っていたわけではありません。利用できるものは利用したのです。

### ヤバいテクニック

1996年、David Siegel氏は『_Creating Killer Web Sites_』という本を出版しました。同書では、HTMLという素材から人目を引くデザインを生み出すための、一連の独創的なテクニックが紹介されています。

そのなかには、1ピクセル四方の大きさの透明なGIF画像を使用するテクニックがありました。それをimg要素としてページ内に挿入し、<code>width</code>および<code>height</code>属性で正確な数値を指定することで、デザイナーはデザイン上の余白の量をコントロールすることができました。

別のテクニックとして、table要素を使うものがありました。この要素は、その子要素であるtr要素やtd要素とともに、表形式のデータを記述することを目的としています。しかし、セルの幅と高さに適切な値を指定することで、お望みのレイアウトならどんなものでも再現するのに用いることができました。

これらはハックであり、厄介な問題に対する巧妙な解決策でした。しかし、それは残念な結果をもたらしました。デザイナーは、HTMLをコンテンツの意味を記述するための言語ではなく、コンテンツの外観を整えるためのツールとして扱っていたのです。CSSは、デザイナーが納得して使うことさえできれば、そうした課題に対する解決策でした。

### ブラウザ戦争

WebデザイナーがCSSを使わなかった理由のひとつに、ブラウザのサポート不足がありました。かつて2つのメジャーなブラウザが、Webの主導権を争っていました。Microsoft Internet ExplorerとNetscape Navigatorです。両者はデザイン的に相容れない存在でした。一方のブラウザが、新しい要素や属性を作ったとします。するともう一方のブラウザは、まったく同じ目的において、異なる独自の要素や属性を作ったのです。

この戦略の背景には、両親のどちらかを選ぶよう迫られた子供のように、Webデザイナーはどちらか一方のプロプライエタリな機能を支持せざるを得なくなる、という思惑があったのでしょう。しかし実際には、Webデザイナーは両方のブラウザ用に制作するほかなく、それは2倍の仕事量を意味します。

あるWebデザイナーのグループは、もううんざりだと感じました。彼らはWeb Standards Projectの旗のもとに集まり、MicrosoftとNetscapeに対し独自の機能拡張を捨て、CSSをはじめとする標準に準拠するように働きかけ始めました。

流れが変わり始めたのは、CSSのサポートに優れたMac版のInternet Explorer 5が登場してからでした。CSSこそWebデザインの未来だとすれば、人生における生産性と創造性は格段に向上することになります。

先進的なWebデザイナーのなかには、早い時期にCSSに注目した人もいました。彼らは、table要素や余白のためのGIF画像を使う代わりに、CSSを使ってWebサイトのデザインを変更しました。Webの創世記の精神に則り、彼らは学んだことを共有し、CSSへの移行を他の人々に促しました。

CSSの能力を最もよく表現していたのは、Dave Shea氏が制作したCSS Zen GardenというWebサイトでしょう。このサイトでは、美しく多様なデザインが紹介されていますが、そのすべてがCSSで実現されています。重要なのは、それらのHTMLが同一であることです。

同じHTML文書が、さまざまにスタイル付けされているのを目にすることで、CSSの効能のひとつである関心の分離を実感することができました。

### Coupling

In any system, from urban infrastructure to a computer programme, the designers of that system can choose the degree to which the pieces of the system depend on one another. In a tightly-coupled system, every piece depends on every piece. In a loosely-coupled system, all the pieces are independent, with little to no knowledge of the other pieces.

In a tightly-coupled system, each part of the system can make assumptions about the other parts. These systems can be designed quite quickly, but at a price. They lack resilience. If one piece fails, it could take the whole system with it.

Designing a loosely-coupled system can take more work. The payoff is that the overall result is more resilient to failure. Individual parts of the system can be swapped out with a minimum of knock-on effects.

The hacks pioneered by David Siegel tightly coupled structure and presentation into a single monolithic HTML file. The adoption of CSS eased this dependency, bringing the web closer to the modular approach of the UNIX philosophy. The presentational information could be moved into a separate file: a style sheet. That's how a single HTML document at the CSS Zen Garden could have so many different designs applied to it.

The style sheet still needs to have some knowledge of the HTML document's structure. Quite often, "hooks" are added into the markup to make it easier to style: specific values of <code>class</code> or <code>id</code> attributes, for example. So HTML and CSS aren't completely decoupled. They form a partnership but they also have an arrangement. The markup document might decide that it wants to try seeing other style sheets sometimes. Meanwhile, the style sheet could potentially be applied to other documents. They are loosely coupled.

## Dancing about architecture

It takes time for a discipline to develop its own design values. Web design is a young discipline indeed. While we slowly begin to form our own set of guiding principles, we can look to other disciplines for inspiration.

The world of architecture has accrued its own set of design values over the years. One of those values is the principle of material honesty. One material should not be used a substitute for another. Otherwise the end result is deceptive.

Using TABLEs for layout is materially dishonest. The TABLE element is intended for marking up the structure of tabular data. The end result of using TABLEs, FONT elements, and spacer GIFs is a façade. At first glance everything looks fine, but it won't stand up to scrutiny. As soon as such a website is stress-tested by actual usage across a range of browsers, the façade crumbles.

Using CSS for presentation is materially honest—that's the intended use of CSS. It also allows HTML to be materially honest. Instead of trying to fulfil two roles—structure and presentation—HTML can return to fulfilling its true purpose, marking up the meaning of content.

It's still possible to use (or abuse) CSS to be materially dishonest. For the longest time, there was no easy way to add rounded corners to an element using CSS. Instead, web designers found ways to hack around the problem, putting background images on the element to simulate the same end effect. It worked up to a point, but just like the spacer GIF hack, it was a façade. Then the <code>border-radius</code> property arrived. Now designers can have their rounded corners in a materially honest way.

Crucially, designers were able to use new properties like <code>border-radius</code> long before every web browser supported them. That's all thanks to the liberal error-handling model of CSS. Newer browsers would display the rounded corners. Older browsers would not throw an error. Older browsers would not stop parsing the CSS and refuse to parse any further. They would simply ignore the instructions they didn't understand and move on. No harm, no foul.

Of course this means that the resulting website will look different in different browsers. Some people will see rounded corners. Others won't.

And that's okay.
