
# Dialogue Acts のアノテーション作業

以下の順序で読むこと．
- [作業の概要](./manuals/Manual.md)
- [ラベル詳細](./manuals/AMI.md)
- [付録](./manuals/Appendix.md)

# ラベルの振り方

```
<label>/<書き起こし>
```

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
