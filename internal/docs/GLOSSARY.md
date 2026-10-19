# GLOSSARY — 用語集

全スコープで同じ意味で使う語。定義の正本は括弧内のスコープ文書。

| 用語 | 定義 | 正本 |
|------|------|------|
| 5 本柱 | 開放する成果物の束。Observatory Hardware / Observatory OS / Observatory Network / Science Data Platform / Research Community | [VISION](VISION.md) |
| Observatory OS | 5 本柱の一つ。観測拠点で動くソフトウェア（S3。S2 の抽象と S4 の拠点内記録を含む） | [VISION](VISION.md) |
| Reality Traceability（背骨） | 柱ではなく、全柱を貫いて検証可能にする証明の連鎖 | [VISION](VISION.md) |
| 核 | 現実世界を観測・記録・検証するための汎用知識基盤。存在論の階層として定める | [VISION](VISION.md) |
| 最初の応用 | 高精度・高信頼な観測を誰でも行えるオープンサイエンス基盤（5 本柱） | [VISION](VISION.md) |
| 最初の題材 | 天文学。核と応用は分野に依存せず、天文学はその試金石 | [VISION](VISION.md) |
| 存在論の階層（Level 0〜8） | 世界観・推定量・時間・空間・信号・観測・来歴・科学・知識。各レベルは下のレベルだけで定義する | [ONTOLOGY](ONTOLOGY.md) |
| 世界／境界／認識 | 存在するものの三区分。世界＝Entity・Event、境界＝Observation、認識＝Measurement・Transformation・Claim・Proof・Theory | [ONTOLOGY](ONTOLOGY.md) |
| Entity（存在物） | 世界に存在するもの。固定の分類を持たない | [ONTOLOGY](ONTOLOGY.md) |
| 宣言される存在／推定される存在 | 存在物の知り方の区別。前者は観測者・センサー・モジュールなどシステム自身が宣言するもの、後者は恒星・人工衛星・大気など同定 Claim でのみ知られるもの | [ONTOLOGY](ONTOLOGY.md) |
| 推定量 | すべての量の形。値・不確かさ・確信度・参照系・来歴の五つからなる。素の値は存在しない | [ONTOLOGY](ONTOLOGY.md) |
| 確信度 | 不確かさの表明そのものの信頼度。信頼の根拠から決まる | [ONTOLOGY](ONTOLOGY.md) |
| 参照系 | 値が何に対して測られているか（時刻系・座標系・単位系など） | [ONTOLOGY](ONTOLOGY.md) |
| 観測時刻（Observed Instant） | 時刻の推定量。完全な時点は観測できないので置かない | [ONTOLOGY](ONTOLOGY.md) |
| 観測区間 | 開始と終了の観測時刻の組。観測は時点ではなく区間を持つ | [ONTOLOGY](ONTOLOGY.md) |
| 位置推定（Position Estimate） | 位置の推定量。速度・姿勢・視線方向も同じ形 | [ONTOLOGY](ONTOLOGY.md) |
| 信号（Signal） | 軸の組（時間・空間・周波数など）の上に並んだ推定量 | [ONTOLOGY](ONTOLOGY.md) |
| Observation（観測） | 観測者・センサー・観測区間・観測者の位置姿勢・信号からなる、世界と認識の唯一の接点。内容は真実ではないが、観測の出来事は事実 | [ONTOLOGY](ONTOLOGY.md) |
| Measurement（測定） | 観測から取り出した推定量。来歴グラフの節点 | [ONTOLOGY](ONTOLOGY.md) |
| Transformation（変換） | 入力の節点 × 手法の版 × パラメータ → 出力の節点。来歴グラフの辺 | [ONTOLOGY](ONTOLOGY.md) |
| Proof | Claim から根の観測まで遡る祖先の部分グラフと、その各辺の前提の充足。保証するのは手続きの正当性 | [ONTOLOGY](ONTOLOGY.md) |
| Theory | 複数の Claim を説明し、事象を予測する仮説。Proof を持たず、Claim によって支持・反証される | [ONTOLOGY](ONTOLOGY.md) |
| 節点／ノード | グラフの要素は節点、観測拠点はノードと呼び分ける | [ONTOLOGY](ONTOLOGY.md) |
| 模型世界 | シミュレーションが観測する世界。そこからの Claim は現実世界についての Claim にならない | [ONTOLOGY](ONTOLOGY.md) |
| モジュール契約 | 制御経路・データ経路・信頼の根拠の宣言・設計の版への参照からなる、全モジュール共通の接続規則 | [HARDWARE](HARDWARE.md) |
| 時刻モジュール | 全機材に共通の信頼の起点となるモジュール。拠点内で共有できる | [HARDWARE](HARDWARE.md) |
| 機材ファミリー | 時刻基準・測定カメラ・全天観測・電波観測・気象観測・移動観測キット | [HARDWARE](HARDWARE.md) |
| 再現可能性の四つ組 | 同じ設計・同じ条件・同じソフト・同じ解析手順。すべて系譜グラフから辿れる | [DECISIONS](DECISIONS.md) |
| 事象（Event） | 世界で起きたこと。対象物ごとの分類の代わりに使う、世界のモデルの単位。システムからは観測を通じて推定されるだけで、その存在も Claim になる | [S1](scopes/S1-ontology.md) |
| 観測者／ノード（Node） | 位置・速度・姿勢が時間とともに変化し、それぞれに不確かさを伴う運動体として表した観測拠点 | [S1](scopes/S1-ontology.md) |
| 6DoF | 位置（3 次元）・姿勢（3 次元回転）の 6 自由度。本設計では速度と各不確かさを伴って観測者を表す | [S1](scopes/S1-ontology.md) |
| 現実トレーサビリティ（Reality Traceability） | 物理現象の発生から科学的主張までの因果関係と前提条件の連鎖そのものを保存・検証対象とする原則 | [S1](scopes/S1-ontology.md) |
| 観測者の軌跡 | 観測者の位置・速度・姿勢と各不確かさの時系列。固定観測所は特殊ケース | [S1](scopes/S1-ontology.md) |
| 仮想ノード | 実在の信号源を持たない観測者。信頼の根拠として「模擬」を宣言する | [S1](scopes/S1-ontology.md) |
| 不確かさ（Uncertainty） | 値と不可分に刻印される最大誤差。時刻・位置・姿勢・計測値のすべてに付き、変換ごとに伝播して消えない | [S1](scopes/S1-ontology.md) |
| 信頼起点（Root of Trust） | 「ここから先は曖昧さも改ざんもない」とする物理的公理。生信号と物理的文脈の出発点 | [S2](scopes/S2-measurement-root-of-trust.md) |
| 信頼の根拠／信頼等級 | 信号源が宣言する、同期の基準・内部処理の透明性・遅延の既知性。主張できる範囲を決める | [S2](scopes/S2-measurement-root-of-trust.md) |
| インシチュ・キャリブレーション | 既知の基準信号へ物理的に切り替え、システム自身の感度・雑音特性を実測・記録する自己校正。校正も既知の入力に対する観測として扱う | [S2](scopes/S2-measurement-root-of-trust.md) |
| 制御経路／高速データ経路 | 機器の制御・状態監視の経路と、生信号を遅延なく流す経路。概念的に分離する | [S2](scopes/S2-measurement-root-of-trust.md) |
| クロスモーダル・トリガー | 異なる分野のセンサー間で連鎖反応を起こすリアクティブ制御 | [S3](scopes/S3-node-runtime.md) |
| 縮退運転（サバイバビリティ） | 資源・環境に応じて維持する計測と間引く処理を自律的に選ぶ運転 | [S3](scopes/S3-node-runtime.md) |
| 観測セッション（Session Bundle） | 目的・時間帯単位で、全ストリーム・空間姿勢履歴・環境・機器構成・校正データを束ねた不可分のパッケージ | [S4](scopes/S4-immutable-record.md) |
| 不変性（Immutability） | 記録済みの生データと文脈を上書き・変更しない性質 | [S4](scopes/S4-immutable-record.md) |
| 遅延同期 | 要約と証明情報を優先して送り、大容量の生データは後から差分同期する永続化モデル | [S4](scopes/S4-immutable-record.md) |
| 誤差剥離 | 生の値を「真の物理量＋各誤差項」の合成とみなし、根拠とともに 1 項ずつ取り除く解析過程 | [S5](scopes/S5-analysis-provenance.md) |
| 観測の型 | 補正段階・前提条件を表す状態。型の不一致となる比較・投入はシステムが拒絶する | [S5](scopes/S5-analysis-provenance.md) |
| プロベナンス（系譜グラフ／来歴グラフ） | 節点（Observation・Measurement・Claim）と辺（Transformation）からなる有向グラフ。根は観測セッション。系譜と来歴は同義 | [S5](scopes/S5-analysis-provenance.md) |
| 内容アドレス型グラフ（Merkle DAG） | 節点が内容の要約で互いを指す有向非巡回グラフ。不変記録・系譜・証明を一つにまとめる概念 | [S5](scopes/S5-analysis-provenance.md) |
| 解析手法（分野別） | 測光・掩蔽など分野ごとの解析。共通の事象モデル上で動き、系譜に記録される | [S5](scopes/S5-analysis-provenance.md) |
| 再計算（Re-computation） | 系譜グラフに従い、過去の生データから新しい手法で派生データを作り直すこと | [S5](scopes/S5-analysis-provenance.md) |
| 科学的主張（Claim） | 結論を、値・不確かさ・要求・証明木を持つ検証可能な構造体として表したもの | [S6](scopes/S6-claim-verification.md) |
| 同定 Claim | 事象と対象（天体など）を結びつける Claim。対象についての主張はこれを前提に持つ | [S6](scopes/S6-claim-verification.md) |
| 合成 Claim | 複数の Claim を証明木の子に持つ Claim | [S6](scopes/S6-claim-verification.md) |
| 要求 | Claim が成立に必要として自ら宣言する条件（不確かさの上限など） | [S6](scopes/S6-claim-verification.md) |
| 証明木（Proof Tree） | Proof を Claim の側から見た形。起点（時刻・機器）・文脈（環境）・変換（補正・導出）の前提を各辺と根に課す | [S6](scopes/S6-claim-verification.md) |
| 自動査読 | 証明木の論理的整合性・要求の充足・ハッシュ連鎖を機械的に検査し、手続きの正当性を検証すること | [S6](scopes/S6-claim-verification.md) |
| 協調スケジューリング | 観測可能な拠点を空間的・気象的に計算し、観測リクエストを自動配分すること | [S7](scopes/S7-distributed-network.md) |
| 大気境界の物理的差分 | 地上と成層圏で同一対象を同時観測し、大気の影響を実測差分として相殺・証明する手法 | [S7](scopes/S7-distributed-network.md) |
| 段階的共有モデル | 検証済み Claim を先に共有し、生データは後から統合するネットワーク共有方式 | [S7](scopes/S7-distributed-network.md) |
| 気づきのインターフェース | 異常・周期性・相関をハイライトし、人間の注意と直感を導く補助。結論は出さない | [S8](scopes/S8-human-discovery.md) |
| 追試（再現実験） | 同じ条件・同じ解析パイプラインを別のデータに適用して結果を確かめること | [S8](scopes/S8-human-discovery.md) |
| 知識の循環 | Theory の予測 → 観測依頼 → 観測 → Claim → Theory の支持・反証、という一周 | [S8](scopes/S8-human-discovery.md) |
