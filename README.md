
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
|Be Positive: Initial Goodbye|bp.ib|
|Be Positive: Return Goodbye|bp.rb|
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

---
以降から追加分．

# stallとfragmentに対する追加作業
`stall`あるいは`fragment`と判断した発言（以下`発言A`）については，`発言A`に後続する一つの発言が`発言A`の終了時刻から1秒以内に開始された場合に限り，`発言A`のラベルが変わる場合には，そのラベルを別途追記する．記法は以下参照．
```
記法）
<stall or fragment>:<別のラベル>/<書き起こし>

例）
f:i/私は
```

# 決め事

## 全体のルール
- 発話ごとにラベリングすること
- 会話を先読みした上でのラベリングは禁止

## stall
ターンをとる時の発言は`stall`になりえる．一方で，ターンをとっている最中の発言は`stall`にはならない．

## fragment
名詞だけの発言は`fragment`にすることができる．一方で，動詞を含む発言は`fragment`にすることができない．

## backchannel vs. assess
日本語では`backchannel`以上の機能を持つ一方，`assess`ほどの機能を持たない発言が多いように感じられます．例えば「なるほど」や「確かに」，「そうですね」など．以上のような発言は`backchannel`とすること．

もちろん非言語情報にも注視し（相手を注視しながら明瞭な声での「そうですね」は`assess`である可能性が高い），適切なラベルを付与するようにしてください．

## suggest vs. elicit-inform vs. elicit-assessment
以上の3つは「自身の考えを述べる意図の強さ」，「相手の考えを求める意図の強さ」が異なる．

`suggest`は自身の考えを述べる意図の強さが強い．例え発言の書き起こしが「順番に意見を言いましょうか**ね**」のように，文末表現が「ね」であったとしても，自身の考えを述べる意図が強ければ`suggest`になりえる．

`elicit-inform`と`elicit-assessment`は，相手の考えを求める意図の強さが強い．

## suggest
議論を方向付けるような発言は`suggest`である．またグループを意思決定へ向けさせるような発言も`suggest`である．

すなわち`suggest`は他者への影響度が強い．

## elicit-inform
情報を尋ねる意図がある`elicit-inform`は，議論のトピックが決まっている状況で生じることが基本的である．

## elicit-assessment
`elicit-assessment`は対話相手に対して明確な評価を求める意図がある．

## assess
`assess`には評価する対象が必要である．言い換えれば，既に登場しているトピックについてのみ`assess`を使用することができる．

例外として，別のトピックについて現在議論している場合，以前のトピックに関しては`assess`できないこととする．基準としては，1分過去に議論されたトピックについては`assess`できない．

`assess`の対象は会話グループの共有情報に限定する．共有情報とは，会話グループのメンバーのいずれかに発言に含まれる情報であり，グループメンバー全員が認識した情報である．その一方，会話参加者は各自資料を参照しながら議論しているが，資料に書いてあるだけでは共有情報とは認めない．

## inform
新しい情報を作り出した発言は`inform`である．

## inform vs. elicit-assessment
例えば，発言「明日は晴れですね」は，`inform`か`elicit-assessment`か．

`inform`には情報を提供する意図がある．一方`elicit-assessment`には対話相手に明確に確認を求める意図がある．従って上の例も，どちらの意図が強いかで判断しなくてはいけない．

一般論として，文末表現が「ね」「よね」の場合，`elicit-assessment`であることが多い．

## elicit-inform vs. eliit-assessment
事実情報を尋ねる意図が強ければ，`elicit-inform`である．一方で評価を尋ねる場合は`eliit-assessment`である．

ここで，`elicit-inform`と`eliit-assessment`はともに，部分ラベルである`Propositional Question`を持つ．`Propositional Question`は「はい」か「いいえ」で返答が可能な問いかけである．従って`elicit-inform (Propositional Question)`は，事実情報を「はい」か「いいえ」で返答することを尋ねるもの（例：猫は哺乳類ですか？）であり，`elicit-assessment (Propositional Question)`は，「はい」か「いいえ」で評価することを尋ねるもの（例：猫は良いと思いますか？）である．

## inform vs. suggest
[付録](./manuals/Appendix.md)も参照のこと．

## とても難しいラベル
例）議論の終盤における「答え出しちゃいますか」．ここでの「答え」は，グループでの意思決定を意味する．

意思決定することを方向付ける意図を強く感じた場合は`suggest`が適当．一方で，他者から意思決定することを方向付ける行動を引き出したい意図を強く感じた場合は`elicit offer or suggestion`が適当．

