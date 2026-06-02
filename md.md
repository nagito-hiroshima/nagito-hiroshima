[← ホーム に戻る](README.md)

> [!NOTE]
> ノートやヒントなど、ユーザーにとって有益な情報を提供するためのセクションです。

> [!TIP]
> ユーザーが特定のタスクを効率的に完了するためのヒントやコツを提供します。

> [!IMPORTANT]
> ユーザーが成功するために必要な重要な情報です。

> [!WARNING]
> 潜在的なリスク due to potential risks.

> [!CAUTION]
> 行動の否定的潜在結果です。


# Mermaid記法メモ
## 記法の種類
### グラフ
#### 右向きのフローチャート
```
flowchart LR
```
```mermaid
flowchart LR
A --> B
```

#### 上下向きのフローチャート
```
flowchart TB
```
```mermaid
flowchart TB
A --> B
```


#### 左右向きのフローチャート
```
flowchart RL
```
```mermaid
flowchart RL
A --> B
```

| 記法 | コード例 | 説明 |
| --- | --- | --- |
| TB　| `flowchart TB` | ↓ |
| TD　| `flowchart TD` | ↓ |
| BT　| `flowchart BT` | ↑ |
| LR　| `flowchart LR` | → |
| RL　| `flowchart RL` | ← |

### ノード
ノードは図の中の「箱」にあたる要素で、囲み記号によって形状が変わります。

| 記法 | 形状 | コード例 |
| --- | --- | --- |
| `A[text]` | 四角形 | `A[四角形ノード]` |
| `A(text)` | 角丸四角形 | `A(角丸ノード)` |
| `A([text])` | スタジアム形 | `A([スタジアム])` |
| `A[[text]]` | サブルーチン | `A[[サブルーチン]]` |
| `A[(text)]` | 円柱（DB） | `A[(データベース)]` |
| `A((text))` | 円 | `A((円ノード))` |
| `A{text}` | ひし形（条件分岐） | `A{条件}` |
| `A{{text}}` | 六角形 | `A{{六角形}}` |
| `A[/text/]` | 平行四辺形 | `A[/入力/]` |
| `A[\text\]` | 逆平行四辺形 | `A[\出力\]` |

```mermaid
flowchart LR
A[四角形] --> B(角丸)
B --> C([スタジアム])
C --> D{ひし形}
D --> E((円))
D --> F{{六角形}}
F --> G[(DB)]
```

## 図の基本構造
#### 1. 基本的なフローチャート
```mermaid
flowchart LR
A --> B
B --> C
C --> D
```
#### 2. ループ（循環）
```mermaid
flowchart LR
A --> B
B --> C
C --> A
```

#### 3. 条件分岐（ひし形ノード）
```mermaid
flowchart TB
START --> 判定{条件は真か?}
判定 -->|Yes| 処理A
判定 -->|No| 処理B
```

#### 4. ノード形状の組み合わせ
```mermaid
flowchart LR
A[状態1] --> B(状態2)
B --> C{状態3}
C --> A
```

#### 5. エッジ（線・矢印）にテキストを付ける
- `A -->|文字つき| B` または `A -- 文字つき --> B` でラベルを付与できる
```mermaid
flowchart LR
A --> B
A --- C
A -->|文字つき| D
A -- 文字つき --- E
```

#### 6. 矢印のスタイル
```mermaid
flowchart LR
A == 太線 === B
A -. 点線 -.- C
A == 太い矢印 ==> D
A -. 点線矢印 .-> E
A -- 丸矢印 --o F
A -- x矢印 --x G
H <-->|双方向矢印| I
H x--x|双方向矢印| J
H o--o|双方向矢印| K
```

#### 7. サブグラフの使用例
```mermaid
flowchart TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```