# .gbapp Guide
![generalbots-2018](https://user-images.githubusercontent.com/65977273/94922431-949c3900-0490-11eb-800a-6b478d689f2a.png)

## Introduction

.gbapp is the folder extension for the General Bots Application package type.
Anything inside a folder considered a .gbapp will be consumed by the server
like a TypeScript application. This conversational application will contain
the source code for custom dialogs and behaviour for any .gbot that associate
this deployed .gbapp.

A good way to start a .gbapp is to find a NPM package to create a .gbapp that
asks for data and output the result. For example, a temperature package can
be installed via `npm install temperature` and then have its methods
convertToKelvin or convertToCelsius called when user asks for conversion. A
.gbapp can persist and read data from database according to the conversation
session.

## Preparing Environment

General procedures:

1. Get SubscriptionId, username and password;
2. Create AppId and Secret;
3. Deploy General Bots;
4. /setupSecurity to get access to Bot Drive;
5. /publish to publish packages on root bot.



### Windows

#### PowerShell Script

Copy and paste on a PowerShell prompt with elavated privileges and when VSCode is opened just press F5 to run the development server.

``` powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

cinst git --confirm
cinst nodejs --confirm --version=14.10.1
cinst vscode --confirm
npm install windows-build-tools -g

&"C:\Program Files\Git\bin\git.exe" clone https://github.com/GeneralBots/BotServer.git
cd BotServer
&"C:\Program Files\Microsoft VS Code\bin\code.cmd" .

```

### Commands to check version of Node.js and NPM.
![verificar](https://user-images.githubusercontent.com/65977273/95104867-bace0d00-070c-11eb-9699-66d3b6134ea5.png)


#### Manual steps.

1. Install [Chocolatey](https://chocolatey.org/install), a Windows Package Manager; 
2. Install [git]( `https://git-scm.com/` ), a Software Configuration Management (SCM) and TortoiseGit; 
3. Install [Node.js](https://npmjs.com/get-npm), a [Runtime system](https://en.wikipedia.org/wiki/Runtime_system); 
4. Install Visual Studio Code Insiders, Brackets or Atom as an editor of your choice;

5. Fork the repository by visiting https://github.com/pragmatismo-io/BotServer/fork;
6. Clone the just forked repository by running `git clone <your-forked-repository-url>/BotServer.git` ; 
7. Run the bot server by `gbot.cmd` .

* Required packages

``` cmd

cinst git --confirm
cinst nodejs --confirm
npm install windows-build-tools -g
cinst tortoisegit --confirm

```

* Optional packages

``` 

cinst 7zip.install --confirm
cinst tortoisegit --confirm
cinst winscp --confirm
cinst sysinternals --confirm
cinst putty --confirm
cinst pandoc --confirm
cinst curl --confirm
cinst micro --confirm
cinst ccleaner --confirm
cinst notepadplusplus --confirm
cinst sql-server-management-studio --confirm

```

* node packages

``` 

npm install -g npm-check-updates
npm install -g cost-of-modules

```

![General Bots Inside Visual Studio Code provides a complete artificial intelligence based conversational platform](https://raw.githubusercontent.com/pragmatismo-io/BotServer/master/docs/images/general-bots-inside-visual-studio-code-provides-a-complete-artificial-intelligence-based-conversational-platform.png)

## Specifications 

## Dialogs

The dialog is built by specifing series of methods, disposed as an array as seen
on Figure 1. Each dialog has also an identifier that can be called by several
engines like kb.gbapp, which handles cloud based search for documents and other
knowledge base information and also routes for the natural language processing
(NLP) engine.

``` typescript

static getDialogs(bot: BotAdapter, min: GBMinInstance) {
    return [{name:"/convertTemperature", waterfall: [
        async step => {
        },
        async step => {
        },
        async step => {
        }]
    },{name:"/convertCurrency", waterfall: [
        async step => {
        },
        async step => {
        },
        async step => {
        }]
    }
    ]
```

    *Figure 1 - How to build dialogs in General Bots using TypeScript*


## Fork concept

Is the implementation of new software based on existing software. The branch takes advantage of the data already used in other software to generate a new one.
This in some way contributes to a better understanding of how it works.

## How To...

### Debugging .gbapp deployed on Azure

1. Visit https://<SITENAME>.scm.azurewebsites.net/api/vfs/LogFiles/Application/index.html


## Tooling

### JavaScript

| Título                                      | Endereço                                                                                          |
|---------------------------------------------|---------------------------------------------------------------------------------------------------|
|                                             | https://deeplearnjs.org/                                                                          |
|                                             | Oimo.js http://lo-th.github.io/Oimo.js/\#stacking                                                 |
|                                             | js-sequence-diagrams: https://bramp.github.io/js-sequence-diagrams/                               |
|                                             | http://blog.avenuecode.com/a-library-for-data-visualization-d3.js                                 |
| Chrome inside Node.js                       | https://github.com/GoogleChrome/puppeteer                                                         |
| XLSX loader                                 | https://github.com/mgcrea/node-xlsx                                                               |
| Node.js bindings for CNTK                   | https://github.com/nadavbar/node-cntk                                                             |
| API Repository                              | https://any-api.com/                                                                              |
| ORM                                         |                                                                                                   |
| Migração de . NET para JavaScript (Node.js) | https://www.reddit.com/r/webdev/comments/2val7s/as_a_net_developer_do_i_need_to_care_about_nodejs |
| Simplified JavaScript Jargon                | http://jargon.js.org                                                                              |

### Packages

| Título | Descrição                        | URL                                |
|--------|----------------------------------|------------------------------------|
| MSAL   | Microsoft Authentication Library | https://www.npmjs.com/package/msal |

### Visual Studio Code Shotcut keys

| Key                      | Description                                                                   |
|--------------------------|-------------------------------------------------------------------------------|
| F8                       | Next error.                                                                   |
| F12                      | Go to symbol definition.                                                      |
| F5                       | Run.                                                                          |
| CTRL + .                 | Auto refactoring (Fix).                                                       |
| ALT + SHIFT + DOWN ARROW | Duplicate the line code.                                                      |
| CTRL + SHIFT + H         | Replace all followed by CTRL + ALT + ENTER on replace text box.               |
| CTRL + SHIFT + B         | Compile inside VSCode, you can also open an external terminal and run tsc -w. |
| CTRL + G                 | Go to the specified line.                                                     |
| CTRL + SHIFT + G         | Goes to Git.                                                                  |
| CTRL + SHIFT+P           | Opens the Command Palette                                                     |
| CTRL + ALT+UP/DOWN ARROW | Enter the Vertical Selection mode                                             |
| ALT + UP/DOWN ARROW      | Move lines                                                                    |


### Visual Studio Code Extensions

| Title                                        | Description                                                     |
|----------------------------------------------|-----------------------------------------------------------------|
| mbinic.tgit-cmds                             | Set of commands for launching TortoiseGit dialogs               |
| tomashubelbauer.vscode-markdown-table-format | Formats MarkDown tables so that all columns have the same width |
| esbenp.prettier-vscode                       | VS Code plugin for prettier/prettier (wraps at column 80)       |
| mikestead.dotenv                             | .env support                                                    |
| abhinavk99.codewall                          | Description here                                                |
| christian-kohler.npm-intellisense            | Description here                                                |
| csholmq.excel-to-markdown-table              | Description here                                                |
| davidanson.vscode-markdownlint               | Description here                                                |
| eg2.ts-tslint                                | Description here                                                |
| eg2.vscode-npm-script                        | Description here                                                |
| esbenp.prettier-vscode                       | Description here                                                |
| formulahendry.auto-rename-tag-               | Description here                                                |
| gruntfuggly.align-mode                       | Description here                                                |
| jmfirth.vsc-space-block-jumper               | Description here                                                |
| kaiwood.indentation-level-movement           | Description here                                                |
| mbinic.tgit-cmds                             | Description here                                                |
| mechatroner.rainbow-csv                      | Description here                                                |
| mikestead.dotenv                             | Description here                                                |
| sirtori.indenticator                         | Description here                                                |
| tandy.color-basic                            | Description here                                                |

## Common tasks

| Task          | Description                         |
|---------------|-------------------------------------|
| npm update -g | Updates NPM                         |
| node -v       | Checks node version                 |
| ncu -a        | Update all packages in package.json |

## Useful documentation 
-https://www.typescriptlang.org/docs/handbook (TypeScript Documentation).
