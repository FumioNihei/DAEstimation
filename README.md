
# Dialogue Acts のアノテーション作業

以下の順序で読むこと．
- [作業の概要](./manuals/Manual.md)
- [AMIラベル](./manuals/AMI.md)
- [議論ラベル](./manuals/Argumentation.md)
- [付録](./manuals/Appendix.md)

# 各ラベルの省略記法

## AMIラベル

|もともと|略記|
|:--|:--|
|Backchannel|bc|
|Stall|s|
|Fragment|f|
|Inform|i|
|Elicit-Inform: Propositional Question|ei.p|
|Elicit-Inform: Check Question|ei.ck|
|Elicit-Inform: Choice Questions|ei.ch|
|Elicit-Inform: Set Question|ei.s|
|Suggest|sg|
|Offer|o|
|Elicit offer-or-suggestion|eos|
|Assess: Agreement|a.ag|
|Assess: Disagreement|a.da|
|Assess: Correction|a.cr|
|Assess: Answer|a.an|
|Assess: Disconfirm|a.dc|
|Assess: Confirm|a.cf|
|Comment-about-Understanding|cau|
|Elicit Assessment: Propositional Question|ea.p|
|Elicit Assessment: Check Question|ea.ck|
|Elicit Assessment: Choice Questions|ea.ch|
|Elicit Assessment: Set Question|ea.s|
|Elicit-Comment-About-Understanding|ea.cau|
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
|OTHER|ot|

## Argumentationラベル

|もともと|略記|
|:--|:--|
|Assertion|a|
|Question|q|
|Retraction|r|
|Concession|c|
|Others|o|

## どうやってラベル付ける？

```
<AMI label>/<argumentation label>
```

とりあえずスラッシュ区切りとする．


例）`Inform`かつ`Assertion`の場合；
```
i/a
```


例）`Elicit Assessment: Propositional Question`かつ`Question`の場合；
```
ea.p/q
```