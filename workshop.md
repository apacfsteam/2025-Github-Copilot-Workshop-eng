author: Your Name
summary: GitHub Copilot Workshop
id: github-copilot-workshop
categories: AI, Development
environments: Web
status: Published
feedback link: https://example.com/feedback

# GitHub Copilot Workshop

## About the Workshop
Duration: 5

Welcome to the GitHub Copilot Workshop! In this workshop, you'll learn how to use GitHub Copilot to explain and improve code.
GitHub Copilot Chat allows you to interact with AI through a chat experience. Let's learn how to use GitHub Copilot through this workshop.

![GitHub Copilot Logo](github-copilot-workshop/img/octocat_copilot.png)

### Today's Goals
- Understand the various features of GitHub Copilot
- Use agent mode to develop new applications

### Prerequisites
- Visual Studio Code must be installed
- Have a GitHub Copilot license
- Have a GitHub account

## Project Setup
Duration: 15

This workshop uses the following GitHub repository:

**Project URL**: https://github.com/moulongzhang/20250708-Python-Project

### Setup Methods

You can start the project using one of the following methods:

### Method 1: Use GitHub Codespaces (Recommended)

1. Open the project URL above in your browser
2. Click the green **Code** button
3. Select the **Codespaces** tab
4. Click **Create codespace on main**

![Codespaces Setup](github-copilot-workshop/img/github-codespaces.png)

> aside positive
>
> **Tip**: Using Codespaces launches the same environment as VS Code in your browser, allowing you to start developing immediately.


### Method 2: Clone to Local Environment

If you have VS Code installed locally:

1. Open terminal or command prompt
2. Clone the repository with the following command:

```bash
git clone https://github.com/moulongzhang/20250708-Python-Project.git
```

3. Navigate to the cloned directory:

```bash
cd 20250708-Python-Project
```

4. Open the project in VS Code:

```bash
code .
```

### Installing Required Extensions

Once you have the project open, install the following extensions:

1. Install the **GitHub Copilot** extension
2. Install the **GitHub Copilot Chat** extension
3. Install the **Python** extension

### Configuration Check

1. Confirm that you are signed in to your GitHub account in VS Code
2. Verify that the Copilot feature is enabled
3. Verify that the Python interpreter is correctly configured

## Try Code Completion
Duration: 10

Let's experience GitHub Copilot's basic code completion features.

### Installing Copilot Extensions

1. Install the **GitHub Copilot** extension
2. Install the **GitHub Copilot Chat** extension

### Configuration Check
Please confirm that sign-in is complete in VS Code.

### Try Code Completion

Create a new Python file and try entering the following comment:

```python
# Function to calculate Fibonacci sequence
def fibonacci(n):
```

Confirm that Copilot automatically suggests code.

> aside positive
>
> **Tip**: Use the `Tab` key to accept suggestions, and `Alt+]` to see the next suggestion.

## GitHub Copilot Next Edit Suggestions Activation Steps
Duration: 10

### Overview
⚙️ [`github.copilot.nextEditSuggestions.enabled`](vscode://settings/github.copilot.nextEditSuggestions.enabled) is a setting that enables GitHub Copilot's next-generation edit suggestion feature. This feature allows you to receive more advanced code editing suggestions.

### 1. Open VS Code

### 2. Access Settings
Open the settings screen using one of the following methods:

#### Method A: From Menu
- **Windows/Linux**: `File` → `Preferences` → `Settings`
- **macOS**: `Code` → `Settings...` → `Settings`

#### Method B: Keyboard Shortcut
- **Windows/Linux**: `Ctrl + ,`
- **macOS**: `Cmd + ,`

#### Method C: Command Palette
- `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (macOS)
- Select `Preferences: Open Settings (UI)`

### 3. Search Settings
Enter the following in the settings search box:
```
github.copilot.nextEditSuggestions.enabled
```

### 4. Enable Setting
- Check the checkbox for the setting item displayed in search results
- Or change `false` to `true`

### 5. Confirm Settings
Verify that the setting has been applied correctly:
- Restart VS Code (recommended)
- Edit code in the editor to confirm that the new suggestion feature is working

### Alternative Method: Direct Editing in settings.json

#### 1. Open settings.json File
- `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (macOS)
- Select `Preferences: Open User Settings (JSON)`

#### 2. Add Setting
```json
{
    "github.copilot.nextEditSuggestions.enabled": true
}
```

#### 3. Save File
- `Ctrl + S` (Windows/Linux) or `Cmd + S` (macOS)

### Let's Try It Out

Please open the `point.py` file included in the project. This file contains a class representing a point in two-dimensional space:

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

Now, we want to extend this class to represent a point in three-dimensional space. First, let's manually change the class name to `Point3D`. Then, GitHub Copilot will suggest the next edit.

> aside positive
>
> **Important**: It may take a little time for Next Edit Suggestion proposals to appear. Please wait patiently.

The suggestion should show changes like:
- Adding `z` parameter to the `__init__` method
- Adding `self.z = z`
- Extending the `distance_to` method for three-dimensional distance calculation
- Displaying z-coordinate in the `__str__` method

In this state, pressing the `Tab` key will move the cursor to the location where GitHub Copilot is making suggestions. To accept the suggestion, press the `Tab` key again.

Then, GitHub Copilot should suggest the next edit. You can also accept this suggestion by pressing the `Tab` key. This way, you can efficiently edit code using Next Edit Suggestion.

### Let's See the Results

Let's continue working on extending the Point2D class to Point3D. You should be able to adapt all methods for three-dimensional space.

Example of expected final code:

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

### Let's Also Try with TODO-commented Code

Please change the commented "二次元" (two-dimensional) in the first line to "三次元" (three-dimensional).

```python
# Class representing a point in two-dimensional space
class Point2D:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def distance_to(self, other):
        # TODO: Add distance calculation code here
        pass
    
    def __str__(self):
        # TODO: Return string representation
        pass
```

Place your cursor after the TODO comments and check Copilot's suggestions.

### Precautions

- Make sure VS Code's GitHub Copilot extension is updated to the latest version
- We recommend restarting VS Code after changing settings

### Troubleshooting

#### When Setting Cannot be Found
1. Confirm that the GitHub Copilot extension is installed
2. Check if the extension is updated to the latest version
3. Restart VS Code and try again

#### When Feature Doesn't Work
1. Confirm that you are logged in to GitHub Copilot
2. Check internet connection
3. Check for error messages in VS Code console

## Copilot Chat Hands-On Preparation
Duration: 5

### Create File

Please save the following file as `delivery_manager.py`.

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

## Explain Code
Duration: 15

Let's have Copilot Chat explain this code.

### Open Copilot Chat

1. Click the **Chat** icon (chat bubble icon) in VS Code's sidebar to open Copilot Chat
2. Or open the Chat panel with `Ctrl+Alt+I` (on macOS `Ctrl+Cmd+I`)

### Check Chat Mode

Confirm that the chat mode is set to "Question" (we'll introduce "Agent" mode later).

### Use /explain Command

1. Type `/explain` in the chat field
2. The `/explain` command will expand in the chat field, showing candidates **@workspace /explain** and **@terminal /explain**
3. Select **@workspace /explain** and type `#delivery_manager.py`
4. Press Enter and Copilot Chat will explain the entire `delivery_manager.py` file

> aside positive
>
> **Tip**: By adding `#` before a filename, you can include the entire file as context.

## Ask About Code Improvement Areas
Duration: 15

### Exercise

Let's ask Copilot Chat about the problematic parts of this code.

### 1. Ask About Overall Class Issues

First, let's ask what kind of problems this code has as a whole class.

Ask Copilot Chat the following:

```
Looking at this DeliveryManager class as a whole, what problems or improvement points are there? Please tell me from the perspectives of design patterns, code quality, and maintainability.
```

### 2. Focus on Specific Methods to Ask About Improvements

Then, let's focus on the `deliver_recipe()` method and ask what methods there are to improve this method.

#### Steps:
1. Type `#deliver_recipe` in the chat field
2. Candidates for code elements (functions, classes, variables, etc.) will be displayed
3. Select the `deliver_recipe` method
4. Enter the following question:

```
What methods are there to improve this deliver_recipe method? Please suggest from the perspectives of readability, performance, and error handling.
```

> aside positive
>
> **Tip**: By using `#`, you can ask questions about specific code elements in a pinpointed way. This allows you to get more specific and useful improvement suggestions.

### Code Review Function

To improve the current code, let's ask Copilot Chat the following:

```
Please improve this Python code. I'd like suggestions from the perspectives of performance, readability, and error handling.
```

### Check from Security Perspective

```
Are there any security issues in this code?
```

### Check Best Practices

```
Please check if this follows Python best practices.
```

## Try Using Agent Mode
Duration: 10

Up to this point, we've been using Copilot Chat in "Question" mode, but now let's try "Agent" mode. Agents can understand user intent and execute tasks more autonomously. Through practical examples, we'll learn how agents function.

### Switching to Agent Mode

First, with the `delivery_manager.py` file open, select "Agent" from the mode selection in Copilot Chat.

<div align="center">
  <img src="github-copilot-workshop/img/agent_mode2.png" alt="Agent mode selection 2" width="600" />
  
  <div style="height: 24;"></div>
  
  <img src="github-copilot-workshop/img/agent_mode.png" alt="Agent mode selection" width="600" />
</div>

### Identifying Problems

After that, try entering the following prompt:

```
Please list the problems that exist in the DeliveryManager class. Then, present improvement suggestions to solve each problem.
```

![Problem analysis by GPT-4.1](github-copilot-workshop/img/agent_GPT4.1.png)

This should suggest multiple improvement points.

### Try with Different Models

By trying the same question with different models, you can compare the characteristics of each model.

![Problem analysis by Claude 4.0](github-copilot-workshop/img/agent_Calude4.0.png)

### Implementing Improvements

Now, let's have the suggested improvements actually implemented.

```
Please implement all the improvement suggestions you provided.
```

Then, Copilot will make direct code changes to the code open in the editor. However, this is still at the suggestion stage, and it's up to the user to decide whether to accept these changes. You can accept or reject them by clicking the "Keep" or "Discard" buttons above the chat field.

### Agent Autonomy

Here, let's check the comments returned by the agent. The agent doesn't just change code according to instructions, but may also confirm that errors are occurring after code changes and try to fix those errors. In appropriate environments, the agent automatically detects errors that occur after code changes and attempts to fix them. In this way, agents can understand user intent and execute tasks more autonomously.

### Command Execution Confirmation

When using agent mode, Copilot may ask whether it's okay to execute commands. This is because Copilot always asks for user confirmation before executing any command. Check the command content, and if there's no problem with execution, click "Allow this time". This allows Copilot to execute that command and make necessary changes.

> aside positive
>
> **Important**: In agent mode, Copilot operates more autonomously, so make sure to carefully check the proposed changes before accepting them.

## Let's Create a Pomodoro Timer
Duration: 30

Up to this point, we've learned the basic usage of GitHub Copilot available on VS Code. Next, let's actually develop an application.

In this hands-on session, we'll develop a Pomodoro timer application. This application has functionality to set work time and break time and manage timers.

We aim to create an application with a UI like the following:

![Pomodoro Timer UI](github-copilot-workshop/img/pomodoro.png)

First, let's create a new Python file on VS Code. Since we want to create this as a web application, we'll use Flask. Let's name the main file "app.py".

### Project Overview

We'll create a web timer application for the Pomodoro Technique.

### Required Features
- 25-minute work timer
- 5-minute break timer
- Timer start/stop/reset
- Progress display and statistics
- Browser notifications and sound notifications
- Responsive web UI

## Consider Pomodoro Timer Design
Duration: 10

First, instead of starting implementation immediately, let's consult with Copilot about what approach and design to proceed with. From here on, we'll proceed entirely in agent mode.

When creating web applications with UI like this time, what's useful is the ability to upload images to Copilot Chat. By using this, you can make Copilot understand the UI image of the application.

First, save the UI image from the previous page as `pomodoro.png` in the project root. Then, click `Add Context` in the chat field and select "Image from Clipboard" or "Files & Folders...". Then select the UI image.

![VS Code Copilot Chat Context Menu](github-copilot-workshop/img/add_context2.png)

![VS Code Copilot Chat Context Menu](github-copilot-workshop/img/add_context3.png)

Once the image is uploaded, it will be displayed in Copilot Chat.

Then, try entering the following prompt:

```
We plan to create a Pomodoro timer web app in this project. The attached image is a UI mock of that app. Please suggest an architecture for creating this app using Flask and HTML/CSS/JavaScript.
```

This will suggest a recommended web application architecture.

If there are points where you think this architecture could be better or areas that lack consideration, try pointing them out. For example, feedback like this:

```
Considering the ease of unit testing, please list any improvements or additions needed in the current architecture.
```

After this exchange has solidified the architecture design, let's save that content to a file once. This way, even if you open a different chat session, you can reference the same architecture content.

```
Since the architecture has been decided through our conversation so far, please compile the web application architecture proposal into a file called architecture.md in the project root, based on the content of our conversation up to this point.
```

> aside positive
>
> When you reach a break in your conversation with Copilot Chat, you can give clearer instructions to Copilot by starting a new conversation. To start a new conversation, click the "New conversation" button at the top of the chat window. At that time, content you want to reference in future chats, like this architecture content, should be written to files and saved as we did here.



## Let's List What Needs to be Done
Duration: 10

Up to this point, we've finalized the UI mock and architecture design. Let's consider what specific features need to be implemented. Let's also consult with Copilot Chat about this. When doing so, let's attach pomodoro.png and architecture.md.

```
Please list the features that need to be implemented to create this Pomodoro timer application.
```

<img src="github-copilot-workshop/img/pomodoro.png" alt="Feature list consideration" width="400" />

![Feature listing example](github-copilot-workshop/img/10-2.list_features.png)

Let's also improve this content through conversation with Copilot. Once the content is finalized, let's save this content to a file called features.md, just like we did with the architecture.

```
Thank you. That content looks good, so please write the list of features that need to be implemented to a file called features.md.
```

Now, we'll start implementation from here, but as a tip for mastering Copilot, instead of trying to implement large features all at once, it's better to start by implementing small features first. This improves the accuracy of the code that Copilot suggests and allows for smoother development progress.

Let's also consult with Copilot about what granularity to break down and implement this application development. Here, let's attach pomodoro.png, architecture.md, and features.md.

```
I want to implement this Pomodoro timer application step by step. Based on the attached image, architecture, and feature list, please suggest a step-by-step implementation plan for what granularity features should be implemented.
```

When I tried it, it suggested a plan consisting of 6 steps. If you have suggestions like "I want this to be done differently," try pointing them out to Copilot. And save this content to a file called plan.md so it can be referenced later. In that case, think about what prompt you should use for instructions.

## Let's Implement
Duration: 30

Now that all the preparation is complete, let's finally start implementation. We'll implement features step by step according to the implementation plan suggested in the previous step.

### Project Structure Preparation

First, let's create a project directory structure according to this architecture.

First, please modify the current project's folder structure to realize the architecture like `architecture.md`. Move files or change configuration files as needed.

Then, after attaching `pomodoro.png`, `architecture.md`, and `plan.md`, let's give Copilot the following instruction:

```
Please implement step 1 of plan.md. At that time, if you need to move files that already exist in this project to another directory, please also perform that work. If there are additional considerations needed, please ask me.
```

Then, in my case, it asked questions that needed consideration as shown below. In such cases, provide the necessary information.

![Example question from Copilot](github-copilot-workshop/img/12-0.question_from_copilot.png)

After that, Copilot implements step 1. Once implementation is complete, Copilot builds the project on its own judgment and checks for errors. If errors occur, it makes additional fixes to resolve those errors. This kind of autonomous behavior is characteristic of agent mode.

Once implementation is complete, let's check the following points:

1. **Directory structure**: Is it structured according to the recommended architecture?
2. **Basic files**: Have necessary basic files (app.py, HTML templates, CSS files, etc.) been created?
3. **Operation check**: Perform simple operation tests to see if any errors are occurring?


The following is the result of step 1 implementation in my case. What kind of application it becomes at this stage will vary from person to person.


![Step 1 implementation result example](github-copilot-workshop/img/12-1.completed_timer.png)




## Let's Write Tests
Duration: 20

Before continuing with implementation, let's write unit tests for the implemented features. By writing unit tests, we can confirm that changes in later steps don't affect existing functionality.

If unit tests have already been implemented at the previous page stage, you can skip this page.

### Test Implementation

Try executing a prompt like the following:

```
There are no unit tests at all for the current implementation, so please implement unit tests.
```

Then, the Copilot agent will ask whether it's okay to use commands to install dependencies for unit testing. Like this, agents always ask users for confirmation before executing any command. Here, click "Continue" to allow execution of necessary commands.

![Test implementation confirmation by Copilot](github-copilot-workshop/img/13-0.test_for_step1.png)

Then, Copilot executes the earlier command in the terminal within VS Code and installs necessary dependencies. Similarly from then on, Copilot always asks users for confirmation before executing any command. If executing that command causes an error, the agent makes additional fixes to resolve that error.


## Let's Implement the Remaining Features
Duration: 20

From here on, let's implement the remaining features step by step as a free exercise.

Here are some points that should be helpful.

### When You Want to Give Instructions for UI

When you want to give instructions for specific elements on the UI, you can make Copilot recognize those elements by uploading UI screenshots to Copilot. In that case, it's good to clearly indicate which element you want to give instructions for by circling particularly noteworthy areas on the screenshot or drawing arrows.

Alternatively, you can upload two screenshots - the current screenshot and the expected screenshot - to have the differences checked and give instructions to get as close as possible to the expected UI.

### When You're Giving the Same Instructions Repeatedly

When writing prompts or specifying context, if you're frequently giving the same instructions, you can make Copilot remember those instructions. Specifically, create a file called `.github/copilot-instructions.md` in the project and write instructions in it. When this file exists, Copilot automatically reads those instructions and can reference them in subsequent chats.

Here's a sample of custom instructions:

```markdown
This project implements a Pomodoro timer with Flask.

The following are important files in the project. Please refer to these files as needed in response to user instructions.
 - `pomodoro.png`: UI mock of the application.
 - `architecture.md`: Architecture document of the application.
 - `features.md`: List of features to implement.
 - `plan.md`: Step-by-step implementation plan.
```

Additionally, by documenting project-specific commands like commands to build the project or execute tests, Copilot will automatically use those commands.

### When Implementation Isn't Progressing Well or Bugs Can't be Resolved

In such cases, try the following approaches:

- Instruct to output debug information and have Copilot analyze that output.
- Try other models.

## Congratulations 🎉
Duration: 5

### What We Learned Today

In this workshop, we learned the following:

- Basic usage of GitHub Copilot
- Code explanation and improvement with Copilot Chat
- Utilizing agent functionality
- Using Copilot in actual application development

### Next Steps

- Try using Copilot in actual projects
- Challenge yourself with more complex application development
- Keep up with new Copilot features

### Resources

- [GitHub Copilot Documentation](https://docs.github.com/copilot)
- [GitHub Copilot Best Practices](https://docs.github.com/copilot/using-github-copilot/best-practices-for-using-github-copilot)

Thank you for your hard work!

お疲れさまでした！