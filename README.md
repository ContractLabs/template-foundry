<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/ContractLabs/template-foundry">
    <img src="https://avatars.githubusercontent.com/u/99892494?s=200&v=4" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">minimal foundry template</h3>
  <p align="center"><img src="https://gifdb.com/images/high/pop-cat-roblox-dance-tk63wxpjc2t2lag8.gif" width="150" height="150"/></p>
  <p align="center">A minimal custom foundry template with deploy, upgrade base script.</p>
  <p align="center">
    <a href="https://github.com/github_username/repo_name/issues">Report Bug</a>
    ·
    <a href="https://github.com/github_username/repo_name/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
  </ol>
</details>


<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Prerequisites

* Install foundry
  ```bash
  curl -L https://foundry.paradigm.xyz | bash
  ```
* More details at: [Foundry installation](https://book.getfoundry.sh/getting-started/installation) 
* Shell setup at: [Shell autocompletion](https://book.getfoundry.sh/config/shell-autocompletion)
### Installation

1. Clone the repo
   ```bash
   git clone https://github.com/ContractLabs/template-foundry.git
   ```
2. Install dependencies packages
   ```bash
   forge install
   ```
<!-- USAGE EXAMPLES -->
## Usage

Use for deploy or upgrade contract. Currently only support 2 type of proxy, UUPS and Transparent.

1. Example
  Configure Deploy.s.script
   ```Solidity
   contract CounterScript is BaseScript {
       function run() public {
          vm.startBroadcast(vm.envUint("PRIVATE_KEY"));
          address deployment = _deployRaw("ERC20", abi.encodeCall(ERC20.initialize, "TokenName", "TokenSymbol"));
          vm.stopBroadcast();
       }
   }
   ```
2. Run script command:
   ```bash
   ./deploy/deploy.sh
   ./deploy/upgrade.sh
   ```

