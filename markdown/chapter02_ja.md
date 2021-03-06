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

### 結合度

都市インフラからコンピュータプログラムに至るまで、どのようなシステムであれ、その設計者は各部が互いに依存する度合いを選ぶことができます。密結合のシステムでは、あらゆる部分が相互に依存しています。疎結合のシステムでは、すべての部分が独立しており、ほかの部分についてほとんど関知しません。

密結合のシステムにおいて、各部は他の部分について仮定をすることができます。そのようなシステムは、非常に迅速に設計することができますが、代償は大きなものです。それはレジリエンスの欠如です。部品が1つでも故障すれば、システム全体が壊れてしまう可能性があります。

疎結合のシステムを設計するには、より多くの作業を要します。しかし、その代償として、システム全体の障害に対する耐久性が向上します。システム個々のパーツを交換しても、その影響は最小限に抑えられます。

David Siegel氏の開発したハックは、構造と表示を単一のモノリシックなHTMLファイルに密結合していました。CSSの採用により、その依存関係が緩和され、WebはUNIX哲学のモジュラーアプローチに近づきました。表示に関する情報は、スタイルシートという別のファイルに移すことができたのです。それこそは、CSS Zen Gardenで単一のHTML文書に数多くのさまざまなデザインを施すことができた理由です。

それでもなおスタイルシートは、HTML文書の構造についてある程度の知識を必要とします。例えば、<code>class</code>属性や<code>id</code>属性で特定の値を指定するといった、スタイル付けを容易にするための「フック」としてのマークアップが、しばしば付け加えられるのです。つまり、HTMLとCSSは完全に切り離されているわけではないのです。両者は、一種のパートナーシップを結んでいますが、同時に取り決めもしています。HTML文書は時々、ほかのスタイルシートを参照しようとするかもしれません。いっぽう、そのスタイルシートは他のHTML文書に適用できる可能性があります。両者はゆるやかに結合しています。

## マテリアルオネスティ

ある専門分野が固有のデザイン価値を生み出すには、時間を要します。Webデザインはまさに、歴史の浅い分野です。分野独自の指針となる原則を私たちが徐々に形成するいっぽう、他の分野からインスピレーションを得ることもできます。

建築の世界では、長年にわたり独自のデザイン価値が蓄積されてきました。その価値のひとつに、「マテリアルオネスティ」​があります。あるマテリアル（素材）を、他のマテリアルの代わりに用いてはいけない。そうしないと、結果的に偽物になってしまうからです。

table要素をレイアウトに使用することは、マテリアル的に不誠実でしょう。table要素は、表形式のデータの構造をマークアップするためのもの。table要素やfont要素、スペーサーGIFを用いた最終的な結果は、ファサード（見せかけ）です。一見するとすべてがうまくいっているように見えますが、精査には耐えられません。そのようなWebサイトが、さまざまなブラウザで実際に使用されるストレステストを受けた途端、見せかけは崩れ去るのです。

CSSを表示に使用することは、マテリアル的に誠実であり、それこそCSSの意図された使い方です。またCSSを使うことで、HTMLをマテリアル的に誠実にすることもできます。HTMLは、構造と表示という2つの役割を果たそうとするのではなく、コンテンツの意味をマークアップするという本来の目的を果たすことができるのです。

CSSを使って（あるいは悪用して）、マテリアル的に不誠実なことをすることは、それでも可能です。長いあいだ、CSSを使って要素の角を丸くする簡単な方法はありませんでした。代わりに、Webデザイナーはこの問題を回避する方法として、背景画像を配置し同じ効果を模擬するやり方を発見しました。それである程度はうまくいきましたが、スペーサーGIFのハックと同様、それはファサードでした。やがて、<code>border-radius</code>というプロパティが登場しました。これでデザイナーは、マテリアル的に誠実なやり方で、角を丸くすることができるようになったのです。

重要なのは、<code>border-radius</code>のような新しいプロパティを、デザイナーはすべてのWebブラウザがサポートするよりずっと前から使用できたことです。これは、CSSの寛大なエラー処理モデルのおかげです。新しいブラウザは角丸を表示します。古いブラウザは、エラーを出力しません。古いブラウザは、CSSの解析を止め、それ以上の解析を拒むこともしませんでした。理解できない指示は無視して、先に進むだけです。害もなければ、不正もありません。

もちろんこれは、完成したWebサイトの見え方がブラウザによって異なることを意味します。角が丸く見える人もいれば、そう見えない人もいるでしょう。

それで問題ありません。
