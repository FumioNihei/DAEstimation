
# Dialogue Acts のアノテーション作業

以下の順序で読むこと．
- [作業の概要](./manuals/Manual.md)
- [ラベル詳細](./manuals/AMI.md)
- [付録](./manuals/Appendix.md)

# ラベルの振り方

```
<label>/<Transcription>
```

`<Transcription>`には，発言の書き起こしが記入されている．変更しないこと．

`<label>`には定義されたラベルの略記（下表参照）を記入すること．

|ラベル|略記|
|:--|:--|
|Backchannel|b|
|Stall|s|
|Fragment|f|
|Inform|i|
|Elicit-Inform: Propositional Question|ei.p|
|Elicit-Inform: Check Question|ei.ck|
|Elicit-Inform: Choice Questions|ei.ch|
|Elicit-Inform: Set Question|ei.s|
|Suggest|sg|
|Offer|of|
|Elicit offer-or-suggestion|eos|
|Assess: Agreement|a.ag|
|Assess: Disagreement|a.da|
|Assess: Correction|a.cr|
|Assess: Answer|a.as|
|Assess: Disconfirm|a.dc|
|Assess: Confirm|a.cf|
|Comment-about-Understanding|cau|
|Elicit Assessment: Propositional Question|ea.p|
|Elicit Assessment: Check Question|ea.ck|
|Elicit Assessment: Choice Questions|ea.ch|
|Elicit Assessment: Set Question|ea.s|
|Elicit-Comment-About-Understanding|ecau|
|Be Positive: Initial Greeting|bp.ig|
|Be Positive: Return Greeting|bp.rg|
|Be Positive: Initial Self-introduction|bp.is|
|Be Positive: Return Self-introduction|bp.rs|
|Be Positive: Apology|bp.a|
|Be Positive: Accept Apology|bp.aa|
|Be Positive: Thanking|bp.t|
|Be Positive: Accept Thanking|bp.at|
|Be Positive: Initial Goodbye|bp.ig|
|Be Positive: Return Goodbye|bp.rg|
|Be Negative|bn|
|OTHER|o|

## 具体例

例1）`Inform`の場合；
```
i/唐揚げとかありますよね
```

例2）`Elicit Assessment: Propositional Question`の場合；
```
ea.p/唐揚げはおいしいと思う？
```


# 決め事

## 全体のルール
- 発話ごとにラベリングすること
- 会話を先読みした上でのラベリングは禁止

## stall
ターンをとる時の発言は`stall`になりえる．一方で，ターンをとっている最中の発言は`stall`にはならない．

## fragment
名詞だけの発言は`fragment`にすることができる．一方で，動詞を含む発言は`fragment`にすることができない．

## stall, fragment
`stall`あるいは`fragment`と判断した発言（以下`発言A`）については，`発言A`に後続する一つの発言が`発言A`の終了時刻から1秒以内に開始された場合に限り，`発言A`のラベルが変わる場合には，別途追記する．記法は以下参照．
```
記法）
<stall or fragment>:<別のラベル>/<書き起こし>

例）
f:i/私は
```

## backchannel vs. assess
日本語では`backchannel`以上の機能を持つ一方，`assess`ほどの機能を持たない発言が多いように感じられます．例えば「なるほど」や「確かに」，「そうですね」など．以上のような発言は`backchannel`とすること．

もちろん非言語情報にも注視し（相手を注視しながら明瞭な声での「そうですね」は`assess`である可能性が高い），適切なラベルを付与するようにしてください．

## suggest vs. elicit-inform vs. elicit-assessment
以上の3つは「自身の考えを述べる意図の強さ」，「相手の考えを求める意図の強さ」が異なる．

`suggest`は自身の考えを述べる意図の強さが強い．例え発言の書き起こしが「順番に意見を言いましょうか**ね**」のように，文末表現が「ね」であったとしても，自身の考えを述べる意図が強ければ`suggest`になりえる．

`elicit-inform`と`elicit-assessment`は，相手の考えを求める意図の強さが強い．

## suggest
議論の方向づけ，suggest

suggest, グループの意思決定を向けさせる，他者への影響度

方針が決まっている，どっちにもはとれない

## elicit-inform
ei, topicが決まっている印象

## elicit-assessment
ea，明確な評価を求めている．

ea, その人の評価

## assess
`assess`には評価する対象が必要である．言い換えれば，既に登場しているトピックについてのみ`assess`を使用することができる．

一方例外として，別のトピックについて既に議論している場合，以前のトピックに関しては`assess`できないこととする．

`assess`の対象は会話グループの共有情報に限定する．共有情報とは，会話グループのメンバーのいずれかに発言に含まれる情報であり，グループメンバー全員が認識した情報である．その一方，会話参加者は各自資料を参照しながら議論しているが，資料に書いてあるだけでは共有情報とは認めない．

## inform

新しい情報を作り出したらinform,

## inform vs. elicit-assessment
inform vs. ea, 明確に確認を求める，「ね」，「よね」がつく場合が多い
i, ea, 尋ねる意図があるか，文末表現


## assess vs. eliit-assessment

a ea, 対象があるかどうか

## elicit-inform vs. eliit-assessment
ei, ea, 事実情報を聞きたいかどうか．


## inform vs. suggest

i sg, 意図を読む，何となく示唆
	suggest, グループの意思決定を向けさせる，他者への影響度

## とても難しいラベル
例）議論の終盤における「答え出しちゃいますか」．ここでの答えは，グループでの意思決定を意味する．

意思決定することを方向付ける意図を強く感じた場合は`suggest`が適当．一方で，他者から意思決定することを方向付ける行動を引き出したい意図を強く感じた場合は`elicit offer or suggestion`が適当．

