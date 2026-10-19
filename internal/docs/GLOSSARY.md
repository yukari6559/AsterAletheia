# GLOSSARY — 用語集

全スコープで同じ意味で使う語。定義の正本は括弧内のスコープ文書。

| 用語 | 定義 | 正本 |
|------|------|------|
| 事象（Event） | 時空間の特定座標において発生・変動した物理現象（信号）。対象物ごとの分類の代わりに使う唯一の単位 | [S1](scopes/S1-ontology.md) |
| 観測者／ノード（Node） | 位置・速度・姿勢が時間とともに変化し、それぞれに不確かさを伴う運動体として表した観測拠点 | [S1](scopes/S1-ontology.md) |
| 6DoF | 位置（3 次元）・姿勢（3 次元回転）の 6 自由度。本設計では速度と各不確かさを伴って観測者を表す | [S1](scopes/S1-ontology.md) |
| 現実トレーサビリティ（Reality Traceability） | 物理現象の発生から科学的主張までの因果関係と前提条件の連鎖そのものを保存・検証対象とする原則 | [S1](scopes/S1-ontology.md) |
| 不確かさ（Uncertainty） | 値と不可分に刻印される最大誤差。時刻・位置・姿勢・計測値のすべてに付く | [S2](scopes/S2-measurement-root-of-trust.md) |
| 信頼起点（Root of Trust） | 「ここから先は曖昧さも改ざんもない」とする物理的公理。生信号と物理的文脈の出発点 | [S2](scopes/S2-measurement-root-of-trust.md) |
| インシチュ・キャリブレーション | 既知の基準信号へ物理的に切り替え、システム自身の感度・雑音特性を実測・記録する自己校正 | [S2](scopes/S2-measurement-root-of-trust.md) |
| 制御経路／高速データ経路 | 機器の制御・状態監視の経路と、生信号を遅延なく流す経路。概念的に分離する | [S2](scopes/S2-measurement-root-of-trust.md) |
| クロスモーダル・トリガー | 異なる分野のセンサー間で連鎖反応を起こすリアクティブ制御 | [S3](scopes/S3-node-runtime.md) |
| 縮退運転（サバイバビリティ） | 資源・環境に応じて維持する計測と間引く処理を自律的に選ぶ運転 | [S3](scopes/S3-node-runtime.md) |
| 観測セッション（Session Bundle） | 目的・時間帯単位で、全ストリーム・空間姿勢履歴・環境・機器構成・校正データを束ねた不可分のパッケージ | [S4](scopes/S4-immutable-record.md) |
| 不変性（Immutability） | 記録済みの生データと文脈を上書き・変更しない性質 | [S4](scopes/S4-immutable-record.md) |
| 遅延同期 | 要約と証明情報を優先して送り、大容量の生データは後から差分同期する永続化モデル | [S4](scopes/S4-immutable-record.md) |
| 誤差剥離 | 生の値を「真の物理量＋各誤差項」の合成とみなし、根拠とともに 1 項ずつ取り除く解析過程 | [S5](scopes/S5-analysis-provenance.md) |
| 観測の型 | 補正段階・前提条件を表す状態。型の不一致となる比較・投入はシステムが拒絶する | [S5](scopes/S5-analysis-provenance.md) |
| プロベナンス（系譜グラフ） | 入力 × アルゴリズムのバージョン × パラメータ ＝ 派生データ、を辺とする有向グラフ | [S5](scopes/S5-analysis-provenance.md) |
| 再計算（Re-computation） | 系譜グラフに従い、過去の生データから新しい手法で派生データを作り直すこと | [S5](scopes/S5-analysis-provenance.md) |
| 科学的主張（Claim） | 結論を検証可能な構造体として表したもの | [S6](scopes/S6-claim-verification.md) |
| 証明木（Proof Tree） | Claim の下に、時刻・機器・環境・論理の証明をツリー状に結合したもの | [S6](scopes/S6-claim-verification.md) |
| 自動査読 | 証明木の論理的整合性とハッシュ連鎖を機械的に検査し、手続きの正当性を検証すること | [S6](scopes/S6-claim-verification.md) |
| 協調スケジューリング | 観測可能な拠点を空間的・気象的に計算し、観測リクエストを自動配分すること | [S7](scopes/S7-distributed-network.md) |
| 大気境界の物理的差分 | 地上と成層圏で同一対象を同時観測し、大気の影響を実測差分として相殺・証明する手法 | [S7](scopes/S7-distributed-network.md) |
| 段階的共有モデル | 検証済み Claim を先に共有し、生データは後から統合するネットワーク共有方式 | [S7](scopes/S7-distributed-network.md) |
| 気づきのインターフェース | 異常・周期性・相関をハイライトし、人間の注意と直感を導く補助。結論は出さない | [S8](scopes/S8-human-discovery.md) |
| 追試（再現実験） | 同じ条件・同じ解析パイプラインを別のデータに適用して結果を確かめること | [S8](scopes/S8-human-discovery.md) |
