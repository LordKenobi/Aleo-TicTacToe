# Aleo Leo Contributor Badge Guide (TicTacToe example)
In this tutorial, I will walk you through everything you need to do to get a contributor badge.
First, go to https://github.com/codespaces, choose a template and you're ready to go.

![image](https://github.com/LordKenobi/TicTacToe-Aleo/assets/158447482/2fa01c7c-f254-4392-8f05-b46835218253)



## **1. The system update**

--> Update the package list, upgrade all installed packages to their latest versions, install git-all and curl packages and switch to the root user.

```shell
#!/bin/bash
sudo apt update && sudo apt upgrade -y
sudo apt-get install git-all -y
sudo apt-get install curl -y
sudo su
```

**-->** Download and install the official compiler for the Rust


```shell
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
After a moment a selection window will appear, enter 1 and confirm to continue with the installation

![image](https://github.com/LordKenobi/TicTacToe-Aleo/assets/158447482/3960fdfe-80a6-4240-bc6d-ffc6520de06d)

--> Set up Cargo (Rust’s build system and package manager)

```shell
source "$HOME/.cargo/env"
```
_Update the package list for upgrades and new package installations_
```shell
sudo apt-get update
```
_Install the build-essential package_
```shell
sudo apt-get install build-essential -y
```
_Install the libc6-dev package_
```shell
sudo apt-get install libc6-dev -y
```
_Run again to ensure that the package list is up-to-date before the next installation_
```shell
sudo apt-get update
```
_Installs the pkg-config package_
```shell
sudo apt-get install pkg-config libssl-dev -y
```
_Run for the final time to ensure that the package list is up-to-date before the final installation_
```shell
sudo apt-get update
```
Note: The -y flag is used to automatically answer "yes" to any prompts that the package manager may encounter during the installation process. This can be useful when running scripts or commands in an automated environment

## **2. Aleo files**

Clone the Aleo files to our template
```shell
git clone https://github.com/AleoHQ/leo
```
```shell
cd leo
```
```shell
cargo install --path .
```

## **3. TicTacToe**

---> For the next part, you will need your LEO private key, which you can find in your wallet settings --> reveal private key

![image](https://github.com/LordKenobi/TicTacToe-Aleo/assets/158447482/992bc552-7a59-432e-9123-3c2d87fa9ea9)

_paste your private key_
```shell
leo account import YOURPRIVATEKEY
```


```shell
leo example tictactoe
```

```shell
cd tictactoe && leo run new
```

```shell
git init -b main && git add .
```

_paste your email adress_
```shell
git config --global user.email "YOUR-EMAIL-ADDRESS"
```

```shell
git commit -m "My first commit"
```

## **4. Github repo**

Now you need to go to https://github.com/new and create a repository
_(for example: TicTacToe-Aleo)_

![image](https://github.com/LordKenobi/TicTacToe-Aleo/assets/158447482/8d699b17-42b7-4694-93df-ca679e494405)

## **5. Token**

You have to create your token, when you are done you will get the key (Important! Remember to write this key down somewhere, as you won't be able to look at it ever again).
_(for example: Aleo)_
https://github.com/settings/tokens/new

![image](https://github.com/LordKenobi/TicTacToe-Aleo/assets/158447482/112dd3d2-8d9c-41ff-8806-783cc4771fbd)


![image](https://github.com/LordKenobi/TicTacToe-Aleo/assets/158447482/89feb529-5c4b-4ac3-9461-14cec7bee694)


## **6. Back to Codespace**
*YOURTOKEN = token key (from point 5)

*USERNAME = your GitHub username

*REPO = github page from point 4 (repository)

```shell
git remote add origin https://YOURTOKEN@github.com/USERNAME/REPO
```
_(our exaple would look like this: git remote add origin https://ghp_*************@github.com/LordKenobi/TicTacToe-Aleo)_

```shell
git remote set-url origin https://YOURTOKEN@github.com/USERNAME/REPO
```
```shell
git push -f origin main
```

## **6.Finish**
You got it, it should look like on the picture below

![image](https://github.com/LordKenobi/TicTacToe-Aleo/assets/158447482/61ccea21-4732-4490-8379-4be9895ce4a7)


Now go to https://github.com/AleoHQ/leo/issues

Choose the "New Issue" Leo Contributor Badge, or if it's not there, just choose "Open a blank issue" and post a message.


__Hi Aleo team! I’m claiming my contributor badge for completing the New Developer Toolkit tutorial._

_Github Username: (your GitHub username)_

_Tutorial Repo: (link to your repository)_

_Requested badge: Tutorial__





## **THAT'S ALL**





<!-- # ⭕ Tic-Tac-Toe -->

[//]: # (<img alt="workshop/tictactoe" width="1412" src="../.resources/tictactoe.png">)

A standard game of Tic-Tac-Toe in Leo.

⭕ ❕ ⭕ ❕ ❌

➖ ➕ ➖ ➕ ➖

⭕ ❕ ⁣❌ ❕ ⭕

➖ ➕ ➖ ➕ ➖

❌ ❕ ❌ ❕ ⭕

## Representing State
Leo allows users to define composite data types with the `struct` keyword. 
The game board is represented by a struct called `Board`, which contains three `Row`s.
An alternative representation would be to use an array, however, these are not yet supported in Leo.

## Language Features
- `struct` declarations
- conditional statements
- early termination. Leo allows users to return from a function early using the `return` keyword.

## Running the Program

Leo provides users with a command line interface for compiling and running Leo programs.

### Providing inputs via the command line.
```bash
leo run <function_name> <input_1> <input_2> ...
```
See `./run.sh` for an example.

## Executing the Program
```bash
leo execute <function_name> <input_1> <input_2> ...
```

## Playing the Game

### 1. Create a new game board
```bash
leo run new
```
|   |   |   |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 0 | 0 |
| 0 | 0 | 0 |

### 2. Player 1 makes a move
```bash
leo run make_move 1u8 1u8 1u8 "{ r1: { c1: 0u8, c2: 0u8, c3: 0u8 }, r2: { c1: 0u8, c2: 0u8, c3: 0u8 }, r3: { c1: 0u8, c2: 0u8, c3: 0u8 } }"
```
|   |   |   |
|---|---|---|
| 1 | 0 | 0 |
| 0 | 0 | 0 |
| 0 | 0 | 0 |

### 3. Player 2 makes a move
```bash
leo run make_move 2u8 2u8 2u8 "{ r1: { c1: 1u8, c2: 0u8, c3: 0u8 }, r2: { c1: 0u8, c2: 0u8, c3: 0u8 }, r3: { c1: 0u8, c2: 0u8, c3: 0u8 } }"
```
|   |   |   |
|---|---|---|
| 1 | 0 | 0 |
| 0 | 2 | 0 |
| 0 | 0 | 0 |
