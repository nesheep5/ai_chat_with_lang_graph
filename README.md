# ai_chat_with_lang_graph

学習目的で、LangGraphを利用した&Q＆Aアプリを作成。

参考書籍: [LangChainとLangGraphによるRAG・AIエージェント［実践］入門](https://amzn.to/3DvNhSi) 

## 実行例
```python
# グラフの実行
initial_state = State(query="生成AIについて教えて下さい")
result = compiled.invoke(initial_state)
```

回答結果
```
生成AI製品エキスパートとしてお答えします。

生成AI（生成的人工知能）は、データから新しいコンテンツを生成する能力を持つAI技術の一種です。
これには、テキスト、画像、音声、音楽など、さまざまな形式のコンテンツが含まれます。
生成AIの代表的な技術には、GPT（Generative Pre-trained Transformer）やGAN（Generative Adversarial Networks）などがあります。

GPTは、特に自然言語処理において強力なツールであり、文章の生成や翻訳、要約などに利用されています。
一方、GANは、画像生成において特に注目されており、リアルな画像を生成する能力があります。

生成AIの応用例としては、クリエイティブなコンテンツ制作、カスタマーサポートの自動化、データの補完や強化、
さらには医療や科学研究における新しい発見の支援などが挙げられます。

この技術は急速に進化しており、倫理的な問題やデータのバイアス、プライバシーの保護など、さまざまな課題も存在します。
しかし、適切に活用することで、多くの分野で革新をもたらす可能性を秘めています。
```

### グラフ構造のビジュアライズ
マーメイド記法での出力
```python
print(compiled.get_graph().draw_mermaid())
```
```mermaid
graph TD;
        __start__([<p>__start__</p>]):::first
        selection(selection)
        answering(answering)
        check(check)
        __end__([<p>__end__</p>]):::last
        __start__ --> selection;
        answering --> check;
        selection --> answering;
        check -. &nbsp;True&nbsp; .-> __end__;
        check -. &nbsp;False&nbsp; .-> selection;
        classDef default fill:#f2f0ff,line-height:1.2
        classDef first fill-opacity:0
        classDef last fill:#bfb6fc
```
