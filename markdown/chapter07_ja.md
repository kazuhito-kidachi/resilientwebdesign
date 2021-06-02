# 第7章：挑戦

The sixth annual conference on hypertext took place in San Antonio, Texas in December 1991. Tim Berners-Lee's World Wide Web project was starting to take shape then. Thinking the conference organisers and attendees would appreciate the project, he submitted a proposal to Hypertext '91. The proposal was rejected.

The hypertext community felt that the World Wide Web project was far too simplistic. Almost every other hypertext system included the concept of two-way linking. If a resource moved, any links pointing to that resource would update automatically. The web provided no such guarantees. Its system of linking was much simpler—you just link to something and that's it. To the organisers of Hypertext '91, this seemed hopelessly naive. They didn't understand that the simplicity of the web was actually its strength. Because linking was so straightforward, anyone could do it. That would prove to be crucial in the adoption and success of the World Wide Web.

It's all-too tempting to quickly declare that an approach is naive, overly simplistic, and unrealistic. The idea that a website can simultaneously offer universal access to everyone while also providing a rich immersive experience for more capable devices ...that also seems hopelessly naive.

This judgement has been handed down many times over the history of the web.

##"This is too simple"

When the Web Standards Project ran its campaign encouraging designers to switch from TABLEs for layout to CSS, it was met with resistance. Time and time again they were criticised for their naivety. "Sure, a CSS-based layout might be fine for a simple personal site but there's no way it could scale to a large complex project."

Then Doug Bowman spearheaded the CSS-based redesign of Wired.com and Mike Davidson led the CSS-based redesign of ESPN.com. After that the floodgates opened.

When Ethan Marcotte demonstrated the power of responsive design, it was met with resistance. "Sure, a responsive design might work for a simple personal site but there's no way it could scale to a large complex project."

Then the Boston Globe launched its responsive site. Microsoft made their homepage responsive. The floodgates opened again.

It's a similar story today. "Sure, progressive enhancement might work for a simple personal site, but there's no way it could scale to a large complex project."

The floodgates are ready to open. We just need you to create the poster child for resilient web design.

##"This is too difficult"

Building resilient websites is challenging. It takes time to apply functionality and features in a considered layered way. The payoff is a website that can better react to unexpected circumstances—unusual browsers, flaky network connections, outdated devices. Nonetheless, for many web designers, the cost in time seems to be too high.

It's worth remembering that building with progressive enhancement doesn't mean that *everything* needs to be made available to *everyone*. Instead it's the core functionality that counts. If every single feature needed to be available to every browser on every device, that would indeed be an impossibly arduous process. This is why prioritisation is so important. As long as the core functionality is available using the simplest possible technology, you can—with a clear conscience—layer on more advanced features.

Still, it's entirely possible that this approach will result in duplicated work. If you build an old-fashioned client-server form submission process and then enhance it with JavaScript, you may end up repeating the form-processing on the client as well as the server. That can be mitigated if you are also using JavaScript on the server. It's theoretically possible to write universal JavaScript so that the server and browser share a single codebase. Even without universal JavaScript, I still think it's worth spending time to create technical credit.

The UK's Government Service design manual provides an even shorter form of the three-step process I've outlined:

1. First, just make it work
2. Second, make it work better

The design manual also explains why:

> If you build pages with the idea that parts other than HTML are optional, you’ll create a better and stronger web page.

This kind of resilience means that the time you spend up-front is well invested. You might also notice an interesting trend; the more you use this process, the less time it will take.

Moving from TABLEs to CSS seemed like an impossibly idealistic goal. Designers were comfortable using TABLE and FONT elements for layout. Why would they want to learn a whole new way of working? I remember how tricky it was to make my first CSS-based layouts after years of using hacks. It took me quite some time. But my second CSS-based layout didn't take quite so long. After a while, it became normal.

Designers comfortable with fixed-width layouts had a hard time with responsive design. That first flexible layout was inevitably going to take quite a while to build. But the second flexible layout didn't take quite so long. After a while, it became normal.

It's no different with the layered approach needed for building resilient websites. If you're not used to working this way, the first time you do it will take quite some time. But the second time won't take quite so long. After a while, it will become normal.

##"How do I convince...?"

The brilliant computer scientist Grace Hopper kept an unusual timepiece on her wall. It ran counter-clockwise. When quizzed on this, she pointed out that it was an arbitrary convention, saying:

> Humans are allergic to change. They love to say, "We've always done it this way." I try to fight that. That's why I have a clock on my wall that runs counter-clockwise.

Behaviour change is hard. Even if you are convinced of the benefits of a resilient approach to web design, you may find yourself struggling to convince your colleagues, your boss, or your clients. It was ever thus. Take comfort from the history of web standards and responsive design. Those approaches were eventually adopted by people who were initially resistant.

Demonstrating the benefits of progressive enhancement can be tricky. Because the payoff happens in unexpected circumstances, the layered approach is hard to sell. Most people will never even know whether or not a site has been built in a resilient way. It's a hidden mark of quality that will go unnoticed by people with modern browsers on new devices with fast network connections.

For that same reason, you can start to implement this layered approach without having to convince your colleagues, your boss, or your clients. If they don't care, then they also won't notice. As Grace Hopper also said, "it's easier to ask forgiveness than it is to get permission."

### ツール

ワークフローやプロセスの変更は、それぞれにおいて使用を前提とするツールと衝突する場合は特に、困難を伴います。ツールは、人々がより効率的な方法で仕事をする手助けとなるものです。ツールは、ワークフローに従属すべきものです。往々にして、ツールが作業方法を決定づけることがあります。WYSIWYGエディタ、グラフィック・デザイン・プログラム、コンテンツ・マネジメント・システム、JavaScriptフレームワークといったツールがワークフローに影響を与えることは、避けられません。

その影響に気づき、認識することができれば、自分に最適なツールを選べるようになります。コードは上手に書かれているか？、開発コミュニティは活発か？、明確なドキュメントは付属しているか？　など、フレームワークの選択にはさまざまな要素があります。しかし、おそらく最も重要なのは、そのフレームワークのアプローチは自身の哲学に合っているか？　という問いです。

人が作ったものである以上、フレームワークにはそれぞれの哲学があります。あなたの哲学がフレームワークの哲学と一致するなら、あなたの仕事はより効率的なものとなるでしょう。しかし、あなたとフレームワークの哲学が衝突するようでは、あらゆる段階であなたはフレームワークと戦うことになります。諦めて、ワークフローをフレームワークに委ねてしまいたくなるかもしれません。そうなったら本末転倒です。

ツールは賢く選びましょう。ソフトウェアとの見解の違いによって、Webデザインに対し回復力あるアプローチを放棄してしまうのは、非常に残念なことです。

Differences of opinion often boil down to a mismatch in priorities. At its heart, the progressive enhancement approach prioritises the needs of people, regardless of their technology. Tools, frameworks, and code libraries, on the other hand, are often built to prioritise the needs of designers and developers. That's not a bad thing. Developer convenience is hugely valuable. But speaking personally, I think that user needs should trump developer convenience.

ある問題に直面したとき、それをユーザー側の問題とするか、私の問題とするか選択できる場合、私は常に後者を選びます。それが私の仕事です。

### 未来に優しく

2011年9月のこと。私よりずっと賢い人々に混じって、テネシー州で催されたとあるカンファレンスで、私は講演をしました。終了後、私たちは田舎に借りた家へ向かい、数日を共にしました。私たちはWebの方向性を探るべく集まったのです。

率直に言って、私たちはパニックになりました。モバイル機器の普及が、すべてを変えてしまったのです。タブレット端末が台頭しました。インターネットテレビの話も出ました。私たちは次の大きなトレンドが何か、知りたいと思っていました。果たしてそれは、インターネット対応の冷蔵庫でしょうか？

結局、私たちが確信できたのは不確実性だけでした：

> 混乱は加速するばかりです。Webにアクセスするのに用いられるデバイス、それも今はまだ想像もつかないようなデバイスの量や多様性は爆発的に増加するでしょう。同時に、そうしたデバイスを利用する人の数と多様性もまた、世界中で増すことでしょう。

それは絶望ではなく、希望の源でもあります。私たちは未来に抗うことも、受け入れることもできます。未来に対して完璧に備えるのは不可能であることを踏まえたうえで、私たちは未来に優しい存在になることを決意しました：

1. 予測できないことを認め、受け入れよう
2. 未来に優しい方法で思考し、振る舞おう
3. 他の人が同じようにする手助けをしよう

最初のステップが最も重要です。予測できないことを認め、受け入れること。それがレジリエントなWebデザインの原動力となります。未来に優しい最良のデザインとは、後方互換性のあるデザインです。

### 前提

Douglas Adamsの著書『Hitchhiker's Guide To The Galaxy（邦題：銀河ヒッチハイク・ガイド）』のなかで、哲学者たちは叫びました。「我々は疑心暗鬼を厳格に定義することを求める！」

パターンマッチングを行う機械のごとく、私たちはトレンドをいち早く察知し、それを前提にコーディングします。Webデザインの歴史において、過去に置かれた前提を少しばかり紹介します：

* 誰もが640ピクセル幅のモニターを使っている
* 誰もがFlashのプラグインをインストールしている
* 誰もが800ピクセル幅のモニターを使っている
* 誰もがマウスとキーボードを使っている
* 誰もが1024ピクセル幅のモニターを使っている
* 誰もがインターネットに高速で接続している

モバイルデバイスの普及は、こうした前提を覆すものでした。モバイルの台頭は、新たに不確実性を生み出したわけではなく、既に存在していた不確実性に光を当てたのです。

それは価値ある教訓となるはずでした。しかし、いつの間にか、古い前提は新しい前提に置き換えられました：

* スマートフォン上で行おうとは決して思わないことが存在する
* あらゆるスマートフォンがタッチスクリーンを備えている
* 誰もが忙しなくスマートフォンを使っている
* すべてのスマートフォン上のあらゆるブラウザーでJavaScriptが機能する

前提とは魅力的なものです。もしも、ある種の前提に同意できたなら、Webデザインはどれほど簡単に扱える存在になっていたことでしょう？

そのサイレンコールは魅力的であると同時に、絶えず変化し続ける不確実なウェブの本質を捉えにくくするものです。Carl Saganは、著書『The Demon-Haunted World（邦題：カール・セーガン 科学と悪霊を語る）』のなかで、次のように述べています：

> どれだけ満足感や安心感が得られようとも、妄想に固執するより宇宙をありのままに把握したほうが、はるかに素晴らしいことです。

## 未来

未来を予測できたらいいのにと思いますが、確実に予測できるのはただひとつ、物事は変化し続けるということだけです。

将来、人々がどのようなデバイスを使ってWebにアクセスするか、Web上でどんなソフトウェアを使うのか、私にはわかりません。

未来は、Webがそうであるように、未知なる存在です。

未来は、Webがそうであるように、あなたが紡ぐものです。
