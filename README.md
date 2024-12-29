# ai_chat_with_lang_graph

学習目的で、LangGraphを利用した&Q＆Aアプリを作成。

参考書籍: [LangChainとLangGraphによるRAG・AIエージェント［実践］入門](https://amzn.to/3DvNhSi) 

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
