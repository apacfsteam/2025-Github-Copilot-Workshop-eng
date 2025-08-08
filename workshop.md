author: Your Name
summary: GitHub Copilot ワークショップ
id: github-copilot-workshop
categories: AI, Development
environments: Web
status: Published
feedback link: https://example.com/feedback

# GitHub Copilot ワークショップ

## ワークショップについて
Duration: 5

GitHub Copilot ワークショップへようこそ！このワークショップでは、GitHub Copilot を使用してコードを説明し、改善する方法を学びます。
GitHub Copilot Chat を使用すると、チャット体験を通じて AI と対話できます。このワークショップを通じて GitHub Copilot の使い方を学びましょう。

![GitHub Copilot Logo](github-copilot-workshop/img/octocat_copilot.png)

### 今日の目標
- GitHub Copilot の様々な機能を理解する
- エージェントモードを使って新しいアプリケーションを開発する

### 前提条件
- Visual Studio Code がインストールされていること
- GitHub Copilot のライセンスを持っていること
- GitHub アカウントを持っていること

## プロジェクトセットアップ
Duration: 15

このワークショップでは以下の GitHub リポジトリを使用します：

**プロジェクト URL**: https://github.com/moulongzhang/20250708-Python-Project

### セットアップ方法

以下のいずれかの方法でプロジェクトを開始できます：

### 方法1: GitHub Codespaces を使用する（推奨）

1. 上記のプロジェクト URL をブラウザで開く
2. 緑色の **Code** ボタンをクリック
3. **Codespaces** タブを選択
4. **Create codespace on main** をクリック

![Codespaces セットアップ](github-copilot-workshop/img/github-codespaces.png)

> aside positive
>
> **ヒント**: Codespaces を使用すると、ブラウザ内で VS Code と同じ環境が起動し、すぐに開発を開始できます。


### 方法2: ローカル環境にクローンする

VS Code がローカルにインストールされている場合：

1. ターミナルまたはコマンドプロンプトを開く
2. 以下のコマンドでリポジトリをクローンする：

```bash
git clone https://github.com/moulongzhang/20250708-Python-Project.git
```

3. クローンしたディレクトリに移動する：

```bash
cd 20250708-Python-Project
```

4. VS Code でプロジェクトを開く：

```bash
code .
```

### 必要な拡張機能のインストール

プロジェクトを開いたら、以下の拡張機能をインストールします：

1. **GitHub Copilot** 拡張機能をインストール
2. **GitHub Copilot Chat** 拡張機能をインストール
3. **Python** 拡張機能をインストール

### 設定確認

1. VS Code で GitHub アカウントにサインインしていることを確認
2. Copilot 機能が有効になっていることを確認
3. Python インタープリターが正しく設定されていることを確認

## コード補完を試してみる
Duration: 10

GitHub Copilot の基本的なコード補完機能を体験してみましょう。

### Copilot 拡張機能のインストール

1. **GitHub Copilot** 拡張機能をインストール
2. **GitHub Copilot Chat** 拡張機能をインストール

### 設定確認
VS Code でサインインが完了していることを確認してください。

### コード補完を試す

新しい Python ファイルを作成し、以下のコメントを入力してみてください：

```python
# フィボナッチ数列を計算する関数
def fibonacci(n):
```

Copilot が自動的にコードを提案することを確認してください。

> aside positive
>
> **ヒント**: `Tab` キーを使って提案を受け入れ、`Alt+]` で次の提案を表示できます。

## GitHub Copilot Next Edit Suggestions 有効化手順
Duration: 10

### 概要
⚙️ [`github.copilot.nextEditSuggestions.enabled`](vscode://settings/github.copilot.nextEditSuggestions.enabled) は GitHub Copilot の次世代編集提案機能を有効化する設定項目です。この機能により、より高度なコード編集提案を受けることができます。

### 1. VS Code を開く

### 2. 設定画面へアクセス
以下のいずれかの方法で設定画面を開きます：

#### 方法A: メニューから
- **Windows/Linux**: `File` → `Preferences` → `Settings`
- **macOS**: `Code` → `Settings...` → `Settings`

#### 方法B: キーボードショートカット
- **Windows/Linux**: `Ctrl + ,`
- **macOS**: `Cmd + ,`

#### 方法C: コマンドパレット
- `Ctrl + Shift + P`（Windows/Linux）または `Cmd + Shift + P`（macOS）
- `Preferences: Open Settings (UI)` を選択

### 3. 設定を検索
設定検索ボックスに以下を入力します：
```
github.copilot.nextEditSuggestions.enabled
```

### 4. 設定を有効化
- 検索結果に表示された設定項目のチェックボックスをチェック
- または `false` を `true` に変更

### 5. 設定を確認
設定が正しく適用されたことを確認します：
- VS Code を再起動（推奨）
- エディターでコードを編集して新しい提案機能が動作することを確認

### 代替方法：settings.json で直接編集

#### 1. settings.json ファイルを開く
- `Ctrl + Shift + P`（Windows/Linux）または `Cmd + Shift + P`（macOS）
- `Preferences: Open User Settings (JSON)` を選択

#### 2. 設定を追加
```json
{
    "github.copilot.nextEditSuggestions.enabled": true
}
```

#### 3. ファイルを保存
- `Ctrl + S`（Windows/Linux）または `Cmd + S`（macOS）

### 実際に試してみる

プロジェクトに含まれる `point.py` ファイルを開いてください。このファイルには二次元空間の点を表すクラスが含まれています：

```python
import math

class Point2D:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def distance_to(self, other):
        dx = self.x - other.x
        dy = self.y - other.y
        return math.sqrt(dx * dx + dy * dy)
    
    def __str__(self):
        return f"Point2D({self.x}, {self.y})"
```

今度は、このクラスを三次元空間の点を表すように拡張したいと思います。まず手動でクラス名を `Point3D` に変更してみましょう。すると GitHub Copilot が次の編集を提案してくれるはずです。

> aside positive
>
> **重要**: Next Edit Suggestion の提案が表示されるまで少し時間がかかる場合があります。辛抱強く待ってください。

提案内容として以下のような変更が表示されるはずです：
- `__init__` メソッドに `z` パラメータの追加
- `self.z = z` の追加
- `distance_to` メソッドを三次元距離計算に拡張
- `__str__` メソッドで z座標の表示

この状態で `Tab` キーを押すと、GitHub Copilot が提案している場所にカーソルが移動します。提案を受け入れるには、再度 `Tab` キーを押してください。

その後、GitHub Copilot は次の編集を提案してくれるはずです。この提案も `Tab` キーで受け入れることができます。このようにして Next Edit Suggestion を使用して効率的にコードを編集できます。

### 結果を見てみる

Point2D クラスを Point3D に拡張する作業を続けてみましょう。すべてのメソッドを三次元空間に対応できるはずです。

期待される最終的なコードの例：

```python
import math

class Point3D:
    def __init__(self, x, y, z):
        self.x = x
        self.y = y
        self.z = z
    
    def distance_to(self, other):
        dx = self.x - other.x
        dy = self.y - other.y
        dz = self.z - other.z
        return math.sqrt(dx * dx + dy * dy + dz * dz)
    
    def __str__(self):
        return f"Point3D({self.x}, {self.y}, {self.z})"
```

### TODO コメント付きのコードでも試してみる

1行目のコメントにある「二次元」を「三次元」に変更してください。

```python
# 二次元空間の点を表すクラス
class Point2D:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def distance_to(self, other):
        # TODO: ここに距離計算のコードを追加
        pass
    
    def __str__(self):
        # TODO: 文字列表現を返す
        pass
```

TODO コメントの後にカーソルを置いて、Copilot の提案を確認してください。

### 注意事項

- VS Code の GitHub Copilot 拡張機能が最新バージョンに更新されていることを確認してください
- 設定変更後は VS Code の再起動をお勧めします

### トラブルシューティング

#### 設定が見つからない場合
1. GitHub Copilot 拡張機能がインストールされていることを確認
2. 拡張機能が最新バージョンに更新されているかチェック
3. VS Code を再起動して再試行

#### 機能が動作しない場合
1. GitHub Copilot にログインしていることを確認
2. インターネット接続をチェック
3. VS Code コンソールでエラーメッセージを確認

## Copilot Chat ハンズオン準備
Duration: 5

### ファイル作成

以下のファイルを `delivery_manager.py` として保存してください。

```python
import time
import random
from typing import List, Callable, Optional
from dataclasses import dataclass, field
from enum import Enum


class EventArgs:
    """イベント引数の基底クラス"""
    pass


class Event:
    """C#のeventに相当するクラス"""
    
    def __init__(self):
        self._handlers: List[Callable] = []
    
    def add_handler(self, handler: Callable):
        """イベントハンドラーを追加"""
        if handler not in self._handlers:
            self._handlers.append(handler)
    
    def remove_handler(self, handler: Callable):
        """イベントハンドラーを削除"""
        if handler in self._handlers:
            self._handlers.remove(handler)
    
    def invoke(self, sender, args: EventArgs = None):
        """イベントを発火"""
        for handler in self._handlers:
            handler(sender, args or EventArgs())


@dataclass
class KitchenObjectSO:
    """キッチンオブジェクトのデータクラス"""
    name: str
    object_id: int


@dataclass
class RecipeSO:
    """レシピのデータクラス"""
    name: str
    kitchen_object_so_list: List[KitchenObjectSO] = field(default_factory=list)


@dataclass
class RecipeListSO:
    """レシピリストのデータクラス"""
    recipe_so_list: List[RecipeSO] = field(default_factory=list)


class PlateKitchenObject:
    """皿のキッチンオブジェクト"""
    
    def __init__(self):
        self._kitchen_object_so_list: List[KitchenObjectSO] = []
    
    def add_kitchen_object(self, kitchen_object: KitchenObjectSO):
        """キッチンオブジェクトを追加"""
        self._kitchen_object_so_list.append(kitchen_object)
    
    def get_kitchen_object_so_list(self) -> List[KitchenObjectSO]:
        """キッチンオブジェクトリストを取得"""
        return self._kitchen_object_so_list.copy()


class KitchenGameManager:
    """キッチンゲームマネージャー（Singleton）"""
    
    _instance: Optional['KitchenGameManager'] = None
    
    def __init__(self):
        self._is_game_playing = False
    
    @classmethod
    def get_instance(cls) -> 'KitchenGameManager':
        """Singletonインスタンスを取得"""
        if cls._instance is None:
            cls._instance = cls()
        return cls._instance
    
    def is_game_playing(self) -> bool:
        """ゲームが進行中かどうか"""
        return self._is_game_playing
    
    def start_game(self):
        """ゲーム開始"""
        self._is_game_playing = True
    
    def stop_game(self):
        """ゲーム停止"""
        self._is_game_playing = False


class DeliveryManager:
    """配達管理クラス（Python版）"""
    
    _instance: Optional['DeliveryManager'] = None
    
    def __init__(self, recipe_list_so: RecipeListSO):
        # イベント定義
        self.on_recipe_spawned = Event()
        self.on_recipe_completed = Event()
        self.on_recipe_success = Event()
        self.on_recipe_failed = Event()
        
        # プライベート変数
        self._recipe_list_so = recipe_list_so
        self._waiting_recipe_so_list: List[RecipeSO] = []
        self._spawn_recipe_timer = 0.0
        self._spawn_recipe_timer_max = 4.0
        self._waiting_recipes_max = 4
        self._successful_recipes_amount = 0
        self._last_update_time = time.time()
    
    @classmethod
    def get_instance(cls, recipe_list_so: RecipeListSO = None) -> 'DeliveryManager':
        """Singletonインスタンスを取得"""
        if cls._instance is None:
            if recipe_list_so is None:
                raise ValueError("初回作成時にはrecipe_list_soが必要です")
            cls._instance = cls(recipe_list_so)
        return cls._instance
    
    def update(self):
        """フレーム更新処理（UnityのUpdate相当）"""
        current_time = time.time()
        delta_time = current_time - self._last_update_time
        self._last_update_time = current_time
        
        self._spawn_recipe_timer -= delta_time
        
        if self._spawn_recipe_timer <= 0.0:
            self._spawn_recipe_timer = self._spawn_recipe_timer_max
            
            kitchen_game_manager = KitchenGameManager.get_instance()
            if (kitchen_game_manager.is_game_playing() and 
                len(self._waiting_recipe_so_list) < self._waiting_recipes_max):
                
                # ランダムにレシピを選択
                waiting_recipe_so = random.choice(self._recipe_list_so.recipe_so_list)
                self._waiting_recipe_so_list.append(waiting_recipe_so)
                
                # イベント発火
                self.on_recipe_spawned.invoke(self)
    
    def deliver_recipe(self, plate_kitchen_object: PlateKitchenObject):
        """レシピの材料と皿の材料が一致しているかどうかを確認する"""
        
        for i, waiting_recipe_so in enumerate(self._waiting_recipe_so_list):
            plate_ingredients = plate_kitchen_object.get_kitchen_object_so_list()
            
            # 材料数が一致するかチェック
            if len(waiting_recipe_so.kitchen_object_so_list) == len(plate_ingredients):
                plate_contents_matches_recipe = True
                
                # レシピの各材料をチェック
                for recipe_kitchen_object_so in waiting_recipe_so.kitchen_object_so_list:
                    ingredient_found = False
                    
                    # 皿の材料と照合
                    for plate_kitchen_object_so in plate_ingredients:
                        if plate_kitchen_object_so == recipe_kitchen_object_so:
                            ingredient_found = True
                            break
                    
                    if not ingredient_found:
                        plate_contents_matches_recipe = False
                        break
                
                # 材料が完全に一致した場合
                if plate_contents_matches_recipe:
                    self._successful_recipes_amount += 1
                    self._waiting_recipe_so_list.pop(i)
                    
                    # 成功イベント発火
                    self.on_recipe_completed.invoke(self)
                    self.on_recipe_success.invoke(self)
                    return
        
        # 一致するレシピが見つからなかった場合
        self.on_recipe_failed.invoke(self)
    
    def get_waiting_recipe_so_list(self) -> List[RecipeSO]:
        """待機中のレシピリストを取得"""
        return self._waiting_recipe_so_list.copy()
    
    def get_successful_recipes_amount(self) -> int:
        """成功したレシピ数を取得"""
        return self._successful_recipes_amount


# 使用例
if __name__ == "__main__":
    # サンプルデータ作成
    tomato = KitchenObjectSO("Tomato", 1)
    lettuce = KitchenObjectSO("Lettuce", 2)
    bread = KitchenObjectSO("Bread", 3)
    
    # サンプルレシピ
    sandwich_recipe = RecipeSO("Sandwich", [bread, lettuce, tomato])
    salad_recipe = RecipeSO("Salad", [lettuce, tomato])
    
    recipe_list = RecipeListSO([sandwich_recipe, salad_recipe])
    
    # ゲームマネージャーとデリバリーマネージャーを初期化
    game_manager = KitchenGameManager.get_instance()
    game_manager.start_game()
    
    delivery_manager = DeliveryManager.get_instance(recipe_list)
    
    # イベントハンドラーの設定
    def on_recipe_spawned(sender, args):
        print("新しいレシピが生成されました！")
    
    def on_recipe_success(sender, args):
        print("レシピ配達成功！")
    
    def on_recipe_failed(sender, args):
        print("レシピ配達失敗...")
    
    delivery_manager.on_recipe_spawned.add_handler(on_recipe_spawned)
    delivery_manager.on_recipe_success.add_handler(on_recipe_success)
    delivery_manager.on_recipe_failed.add_handler(on_recipe_failed)
    
    # サンプル実行
    print("ゲーム開始...")
    
    # 5秒間更新処理を実行
    start_time = time.time()
    while time.time() - start_time < 5:
        delivery_manager.update()
        time.sleep(0.1)  # 100ms間隔で更新
    
    print(f"待機中のレシピ数: {len(delivery_manager.get_waiting_recipe_so_list())}")
    
    # サンプル配達テスト
    plate = PlateKitchenObject()
    plate.add_kitchen_object(bread)
    plate.add_kitchen_object(lettuce)
    plate.add_kitchen_object(tomato)
    
    print("サンドイッチを配達...")
    delivery_manager.deliver_recipe(plate)
    
    print(f"成功したレシピ数: {delivery_manager.get_successful_recipes_amount()}")
```

## コードを説明してもらう
Duration: 15

Copilot Chat にこのコードを説明してもらいましょう。

### Copilot Chat を開く

1. VS Code のサイドバーにある **Chat** アイコン（チャット吹き出しアイコン）をクリックして Copilot Chat を開く
2. または `Ctrl+Alt+I`（macOS では `Ctrl+Cmd+I`）でチャットパネルを開く

### チャットモードを確認

チャットモードが「Question」に設定されていることを確認してください（「Agent」モードについては後で紹介します）。

### /explain コマンドを使う

1. チャット欄に `/explain` と入力
2. `/explain` コマンドがチャット欄で展開され、**@workspace /explain** と **@terminal /explain** の候補が表示される
3. **@workspace /explain** を選択して `#delivery_manager.py` と入力
4. Enter キーを押すと Copilot Chat が `delivery_manager.py` ファイル全体を説明してくれる

> aside positive
>
> **ヒント**: ファイル名の前に `#` を付けることで、ファイル全体をコンテキストとして含めることができます。

## コードの改善点について聞いてみる
Duration: 15

### 演習

このコードの問題点について Copilot Chat に聞いてみましょう。

### 1. クラス全体の問題点について聞く

まず、このコードが全体的にどのような問題を抱えているかを聞いてみましょう。

Copilot Chat に以下のように聞いてみてください：

```
この DeliveryManager クラス全体を見て、どのような問題点や改善点がありますか？設計パターン、コード品質、保守性の観点から教えてください。
```

### 2. 特定のメソッドに絞って改善点を聞く

次に、`deliver_recipe()` メソッドに焦点を当てて、このメソッドを改善する方法について聞いてみましょう。

#### 手順：
1. チャット欄に `#deliver_recipe` と入力
2. コード要素（関数、クラス、変数など）の候補が表示される
3. `deliver_recipe` メソッドを選択
4. 以下の質問を入力：

```
この deliver_recipe メソッドを改善するにはどのような方法がありますか？可読性、パフォーマンス、エラーハンドリングの観点から提案してください。
```

> aside positive
>
> **ヒント**: `#` を使用することで、特定のコード要素にピンポイントで質問できます。これにより、より具体的で有用な改善提案を得ることができます。

### コードレビュー機能

現在のコードを改善するために、Copilot Chat に以下のように聞いてみましょう：

```
この Python コードを改善してください。パフォーマンス、可読性、エラーハンドリングの観点から提案をお願いします。
```

### セキュリティの観点からチェック

```
このコードにセキュリティ上の問題はありますか？
```

### ベストプラクティスのチェック

```
これが Python のベストプラクティスに従っているかチェックしてください。
```

## エージェントモードを使ってみる
Duration: 10

ここまでは Copilot Chat を「Question」モードで使用してきましたが、今度は「Agent」モードを試してみましょう。エージェントはユーザーの意図を理解し、より自律的にタスクを実行できます。実際の例を通して、エージェントがどのように機能するかを学びましょう。

### エージェントモードへの切り替え

まず、`delivery_manager.py` ファイルを開いた状態で、Copilot Chat のモード選択から「Agent」を選択してください。

<div align="center">
  <img src="github-copilot-workshop/img/agent_mode2.png" alt="エージェントモード選択2" width="600" />
  
  <div style="height: 24;"></div>
  
  <img src="github-copilot-workshop/img/agent_mode.png" alt="エージェントモード選択" width="600" />
</div>

### 問題の特定

その後、以下のプロンプトを入力してみてください：

```
DeliveryManager クラスに存在する問題点をリストアップしてください。そして、それぞれの問題を解決するための改善提案を示してください。
```

![GPT-4.1による問題分析](github-copilot-workshop/img/agent_GPT4.1.png)

これにより、複数の改善点が提案されるはずです。

### 異なるモデルで試してみる

同じ質問を異なるモデルで試すことで、各モデルの特徴を比較できます。

![Claude 4.0による問題分析](github-copilot-workshop/img/agent_Calude4.0.png)

### 改善の実装

次に、提案された改善を実際に実装してもらいましょう。

```
提案された改善をすべて実装してください。
```

すると、Copilot はエディターで開いているコードに直接コード変更を行います。ただし、これはまだ提案段階であり、これらの変更を受け入れるかどうかはユーザーが決定します。チャット欄の上にある「Keep」または「Discard」ボタンをクリックして、変更を受け入れるか拒否することができます。

### エージェントの自律性

ここで、エージェントが返すコメントを確認してみましょう。エージェントは単に指示に従ってコードを変更するだけでなく、コード変更後にエラーが発生していることを確認し、そのエラーを修正しようとすることがあります。適切な環境では、エージェントはコード変更後に発生するエラーを自動的に検出し、それらのエラーを修正しようと試みます。このようにして、エージェントはユーザーの意図を理解し、より自律的にタスクを実行できます。

### コマンド実行の確認

エージェントモードを使用する際、Copilot はコマンドを実行してよいかどうか確認することがあります。これは Copilot が任意のコマンドを実行する前に、常にユーザーの確認を求めるためです。コマンドの内容を確認し、実行に問題がなければ「Allow this time」をクリックしてください。これにより、Copilot はそのコマンドを実行し、必要な変更を行うことができます。

> aside positive
>
> **重要**: エージェントモードでは、Copilot がより自律的に動作するため、提案された変更を受け入れる前に注意深く確認してください。

## ポモドーロタイマーを作ってみる
Duration: 30

ここまで、VS Code で利用可能な GitHub Copilot の基本的な使い方を学びました。次に、実際にアプリケーションを開発してみましょう。

このハンズオンでは、ポモドーロタイマーアプリケーションを開発します。このアプリケーションは作業時間と休憩時間を設定し、タイマーを管理する機能を持ちます。

以下のような UI を持つアプリケーションの作成を目指します：

![ポモドーロタイマー UI](github-copilot-workshop/img/pomodoro.png)

まず、VS Code で新しい Python ファイルを作成しましょう。Web アプリケーションとして作成したいので、Flask を使用します。メインファイルは「app.py」という名前にしましょう。

### プロジェクト概要

ポモドーロテクニック用の Web タイマーアプリケーションを作成します。

### 必要な機能
- 25分の作業タイマー
- 5分の休憩タイマー
- タイマーの開始/停止/リセット
- 進捗表示と統計
- ブラウザ通知と音声通知
- レスポンシブな Web UI

## ポモドーロタイマーの設計を考える
Duration: 10

まず、すぐに実装を始めるのではなく、どのようなアプローチと設計で進めるべきかを Copilot に相談してみましょう。ここからは完全にエージェントモードで進めます。

今回のように UI を持つ Web アプリケーションを作成する際に便利なのが、Copilot Chat に画像をアップロードする機能です。これを使うことで、アプリケーションの UI イメージを Copilot に理解させることができます。

まず、前のページの UI 画像を `pomodoro.png` としてプロジェクトルートに保存します。そして、チャット欄の `Add Context` をクリックし、「Image from Clipboard」または「Files & Folders...」を選択します。そして UI 画像を選択してください。

![VS Code Copilot Chat Context Menu](github-copilot-workshop/img/add_context2.png)

![VS Code Copilot Chat Context Menu](github-copilot-workshop/img/add_context3.png)

画像がアップロードされると、Copilot Chat に表示されます。

そして、以下のようなプロンプトを入力してみてください：

```
このプロジェクトでポモドーロタイマーの Web アプリを作成する予定です。添付した画像がそのアプリの UI モックです。Flask と HTML/CSS/JavaScript を使ってこのアプリを作成するためのアーキテクチャを提案してください。
```

これにより、推奨される Web アプリケーションアーキテクチャが提案されます。

このアーキテクチャをもっとよくできる点や考慮が足りない部分があると思った場合は、指摘してみてください。例えば、このようなフィードバックです：

```
単体テストのしやすさを考慮して、現在のアーキテクチャで必要な改善や追加すべき点があれば教えてください。
```

このやり取りでアーキテクチャ設計が固まったら、その内容を一度ファイルに保存しましょう。こうすることで、別のチャットセッションを開いても、同じアーキテクチャ内容を参照できるようになります。

```
これまでの会話でアーキテクチャが決まったので、これまでの会話内容をもとに、Web アプリケーションのアーキテクチャ提案を architecture.md というファイル名でプロジェクトルートに作成してください。
```

> aside positive
>
> Copilot Chat との会話で一区切りついた際は、新しい会話を開始することで、Copilot により明確な指示を与えることができます。新しい会話を開始するには、チャットウィンドウの上部にある「新しい会話」ボタンをクリックします。その際、今回のアーキテクチャ内容のように、今後のチャットで参照したい内容は、ここで行ったようにファイルに書き出して保存しておくとよいでしょう。



## やるべきことをリストアップしてみる
Duration: 10

ここまでで、UI モックとアーキテクチャ設計が固まりました。具体的にどのような機能を実装する必要があるかを考えてみましょう。これについても Copilot Chat に相談してみましょう。その際は、pomodoro.png と architecture.md を添付します。

```
このポモドーロタイマーアプリケーションを作成するために実装すべき機能をリストアップしてください。
```

<img src="github-copilot-workshop/img/pomodoro.png" alt="機能リスト検討" width="400" />

![機能リスト例](github-copilot-workshop/img/10-2.list_features.png)

この内容も Copilot との会話を通じて改良してみましょう。内容が確定したら、アーキテクチャの時と同じように、この内容を features.md というファイル名で保存しましょう。

```
ありがとうございます。その内容で良いので、実装すべき機能のリストを features.md というファイルに書き出してください。
```

ここから実装に入りますが、Copilot を使いこなすためのコツとして、いきなり大きな機能を一度に実装しようとするのではなく、小さな機能から実装を始めることが重要です。これにより、Copilot が提案するコードの精度が向上し、開発の進行がスムーズになります。

このアプリケーション開発をどのような粒度で分割して実装すればよいかも、Copilot に相談してみましょう。ここでは pomodoro.png、architecture.md、features.md を添付します。

```
このポモドーロタイマーアプリケーションを段階的に実装したいと思います。添付した画像、アーキテクチャ、機能リストに基づいて、どのような粒度で機能を実装すべきか、段階的な実装計画を提案してください。
```

私が試したときは、6つのステップからなる計画が提案されました。「これはこのようにしてほしい」といった希望がある場合は、Copilot に指摘してみてください。そして、この内容を plan.md というファイル名で保存して、後で参照できるようにしましょう。その場合、どのようなプロンプトで指示すればよいか考えてみてください。

## 実装してみる
Duration: 30

すべての準備が整いました。いよいよ実装を開始しましょう。前のステップで提案された実装計画に従って、機能を段階的に実装していきます。

### プロジェクト構造の準備

まず、このアーキテクチャに従ってプロジェクトのディレクトリ構造を作成しましょう。

まず、`architecture.md` のようなアーキテクチャを実現するために、現在のプロジェクトのフォルダ構造を変更してください。ファイルの移動や設定ファイルの変更が必要に応じて行ってください。

そして、`pomodoro.png`、`architecture.md`、`plan.md` を添付した後、Copilot に以下の指示を与えてみましょう：

```
plan.md のステップ 1 を実装してください。その際、このプロジェクトに既に存在するファイルを別のディレクトリに移動する必要がある場合は、その作業も合わせて行ってください。追加で検討が必要な点があれば質問してください。
```

すると、私の場合は以下のような検討が必要な質問がありました。このような場合は、必要な情報を提供してください。

![Copilot からの質問例](github-copilot-workshop/img/12-0.question_from_copilot.png)

その後、Copilot がステップ 1 を実装します。実装が完了すると、Copilot は独自の判断でプロジェクトをビルドし、エラーをチェックします。エラーが発生した場合、そのエラーを解決するための追加の修正を行います。このような自律的な動作は、エージェントモードの特徴です。

実装が完了したら、以下の点を確認してみましょう：

1. **ディレクトリ構造**: 推奨されたアーキテクチャに従って構造化されているか？
2. **基本ファイル**: 必要な基本ファイル（app.py、HTML テンプレート、CSS ファイルなど）が作成されているか？
3. **動作確認**: 簡単な動作テストを行ってエラーが発生していないか？


以下は私の場合のステップ 1 実装結果です。この段階でどのようなアプリケーションになるかは人それぞれです。


![ステップ 1 実装結果例](github-copilot-workshop/img/12-1.completed_timer.png)




## テストを書いてみる
Duration: 20

実装を続ける前に、実装した機能に対して単体テストを書いてみましょう。単体テストを書くことで、後のステップでの変更が既存の機能に影響しないことを確認できます。

前のページの段階で単体テストが既に実装されている場合は、このページはスキップできます。

### テスト実装

以下のようなプロンプトを実行してみてください：

```
現在の実装には単体テストが全くないので、単体テストを実装してください。
```

すると、Copilot エージェントは単体テストのために依存関係をインストールするためのコマンドを実行してよいかどうか確認してきます。このように、エージェントは任意のコマンドを実行する前に、常にユーザーに確認を求めます。ここでは「Continue」をクリックして、必要なコマンドの実行を許可してください。

![Copilot によるテスト実装確認](github-copilot-workshop/img/13-0.test_for_step1.png)

すると、Copilot は VS Code 内のターミナルで先ほどのコマンドを実行し、必要な依存関係をインストールします。同様に、それ以降も Copilot は任意のコマンドを実行する前に常にユーザーに確認を求めます。そのコマンドを実行してエラーが発生した場合、エージェントはそのエラーを解決するための追加の修正を行います。


## 残りの機能を実装してみる
Duration: 20

ここからは、残りの機能を段階的に実装していく自由演習となります。

参考になるポイントをいくつか紹介します。

### UI について指示を出したい場合

UI の特定の要素について指示を出したい場合は、UI のスクリーンショットを Copilot にアップロードしてその要素を認識させることができます。その際、スクリーンショット上で特に注目してほしい箇所を丸で囲ったり矢印を描いたりして、どの要素について指示を出したいかを明確にするとよいでしょう。

または、現在のスクリーンショットと期待するスクリーンショットの2つをアップロードして、差分をチェックしてもらい、期待する UI に可能な限り近づけるための指示を出すこともできます。

### 同じ指示を繰り返し出している場合

プロンプトの作成やコンテキストの指定で、頻繁に同じ指示を出している場合は、Copilot にその指示を記憶させることができます。具体的には、プロジェクトに `.github/copilot-instructions.md` というファイルを作成し、そこに指示内容を書いておきます。このファイルが存在すると、Copilot は自動的にその指示を読み込み、以降のチャットでその内容を参照できるようになります。

カスタム指示の例：

```markdown
このプロジェクトは Flask を使ったポモドーロタイマーの実装です。

プロジェクトの重要なファイルは以下です。ユーザーの指示に応じて、これらのファイルを必要に応じて参照してください。
 - `pomodoro.png`: アプリケーションの UI モック
 - `architecture.md`: アプリケーションのアーキテクチャドキュメント
 - `features.md`: 実装すべき機能のリスト
 - `plan.md`: 段階的な実装計画
```

さらに、プロジェクトをビルドするコマンドやテストを実行するコマンドなど、プロジェクト固有のコマンドをドキュメント化することで、Copilot がそれらのコマンドを自動的に使用するようになります。

### 実装がうまく進まない場合やバグが解決できない場合

このような場合は、以下のアプローチを試してみてください：

- デバッグ情報を出力するように指示し、その出力を Copilot に分析してもらう
- 他のモデルを試してみる

## おめでとうございます 🎉
Duration: 5

### 今日学んだこと

このワークショップでは以下のことを学びました：

- GitHub Copilot の基本的な使い方
- Copilot Chat を使ったコードの説明と改善
- エージェント機能の活用
- 実際のアプリケーション開発での Copilot の利用

### 次のステップ

- 実際のプロジェクトで Copilot を使ってみる
- より複雑なアプリケーション開発にチャレンジする
- Copilot の新機能を継続的にキャッチアップする

### リソース

- [GitHub Copilot ドキュメント](https://docs.github.com/copilot)
- [GitHub Copilot ベストプラクティス](https://docs.github.com/copilot/using-github-copilot/best-practices-for-using-github-copilot)

お疲れ様でした！