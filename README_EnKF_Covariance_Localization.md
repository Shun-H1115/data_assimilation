# アンサンブルカルマンフィルタの共分散局所化に関する論文レビュー

本報告書では、アンサンブルカルマンフィルタ（EnKF）の共分散局所化に関する主要な論文を 3 本紹介し、それぞれの概要、モデル式、出典をまとめています。

---

## 論文 1: "Data Assimilation Using an Ensemble Kalman Filter Technique"

- **概要**: 本論文では、アンサンブルカルマンフィルタ（EnKF）を用いたデータ同化手法を提案し、特に共分散局所化の重要性を強調しています。局所化により、アンサンブルサイズが小さい場合でも信頼性の高い同化結果が得られることを示しています。
- **モデル式**:
  共分散局所化は、背景誤差共分散行列 $$ \mathbf{P}^f $$ に対して距離に基づく減衰関数（例: ガスパリ・コーン関数）を適用することで実現されます。これにより、遠方の観測が状態更新に与える影響を減少させ、スプリアスな相関を抑制します。
- **出典**: Houtekamer, P. L., & Mitchell, H. L. (1998). _Data Assimilation Using an Ensemble Kalman Filter Technique_. Monthly Weather Review, 126(3), 796–811.

---

## 論文 2: "A Local Ensemble Kalman Filter for Atmospheric Data Assimilation"

- **概要**: 本研究では、局所アンサンブルカルマンフィルタ（LEKF）を導入し、各観測点周辺の局所的な領域でデータ同化を行う手法を提案しています。これにより、大規模システムにおける計算効率と精度の向上を実現しています。
- **モデル式**:
  LEKF では、局所的な背景誤差共分散行列 $$ \mathbf{P}^f*{ ext{local}} $$ を計算し、カルマンゲイン $$ \mathbf{K}*{ ext{local}} $$ を次式で求めます:
  $$
  \mathbf{K}_{	ext{local}} = \mathbf{P}^f_{	ext{local}} \mathbf{H}^T (\mathbf{H} \mathbf{P}^f_{	ext{local}} \mathbf{H}^T + \mathbf{R})^{-1}
  $$
  ここで、$$ \mathbf{H} $$ は観測演算子、$$ \mathbf{R} $$ は観測誤差共分散行列です。
- **出典**: Ott, E., Hunt, B. R., Szunyogh, I., et al. (2004). _A Local Ensemble Kalman Filter for Atmospheric Data Assimilation_. Tellus A, 56(5), 415–428.

---

## 論文 3: "The Local Ensemble Transform Kalman Filter and Its Implementation"

- **概要**: 本論文では、局所アンサンブル変換カルマンフィルタ（LETKF）の理論と実装方法を詳述しています。LETKF は、各格子点で独立にデータ同化を行うことで、高効率かつ高精度な解析を可能にしています。
- **モデル式**:
  LETKF では、アンサンブルメンバーの線形結合を用いて解析場を構築します。解析アンサンブル $$ \mathbf{X}^a $$ は、予報アンサンブル $$ \mathbf{X}^f $$ と重み行列 $$ \mathbf{W}^a $$ を用いて次式で表されます:
  $$
  \mathbf{X}^a = \mathbf{X}^f \mathbf{W}^a
  $$
  重み行列 $$ \mathbf{W}^a $$ は、観測と予報の誤差共分散を考慮して計算されます。
- **出典**: Hunt, B. R., Kostelich, E. J., & Szunyogh, I. (2007). _Efficient Data Assimilation for Spatiotemporal Chaos: A Local Ensemble Transform Kalman Filter_. Physica D, 230(1–2), 112–126.

---

## まとめ

これらの論文は、アンサンブルカルマンフィルタにおける共分散局所化の理論的基盤と実践的応用を深く探求しています。詳細は各出典をご参照ください。
