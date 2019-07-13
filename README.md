<p align="center"><img src="./src/logo.jpg" align="center"></p>
<h1 align="center">pay-no-load</h1>
<p><h3 align="center">A plugin for the Alethio Ethereum lite-explorer</h3></p>

---

<p align="center">:tada::tada::tada::tada:</p>
<img src="src/gifs/alethio-plugin.gif" alt="alethio-plugin" style="width:80%; margin-left: auto; margin-right: auto; display: block">

## Setting up the lite-explorer and the plugin

1. Clone the lite-explorer repo, and run the following commands in your terminal, one by one :

```javascript
$ git clone https://github.com/Alethio/ethereum-lite-explorer.git
$ cd ethereum-lite-explorer
$ npm install
$ cp config.default.json config.dev.json
```

2. Now, in another terminal tab, clone the plugin github repo, inside _ethereum-lite-explorer_ :

```javascript
$ git clone https://github.com/smitrajput/pay-no-load.git
```

3. Remove the version query strings `?v=#.#.#` from the "plugins" URIs in `config.dev.json`.

4. Build the lite-explorer:
   `npm run build`

5. Now, in another terminal tab, _while inside ethereum-lite-explorer_ install `cms-plugin-tool` and the plugins by running:

```javascript
$ npm i -g @alethio/cms-plugin-tool@1.0.0-beta.2
$ acp install --dev \
    @alethio/explorer-plugin-eth-common \
    @alethio/explorer-plugin-eth-lite \
    @alethio/explorer-plugin-3box
    smitrajput/pay-no-load
```

4. Change into the plugin repo, install node packages and build the modules:

```javascript
$ cd pay-no-load
$ npm install
$ npm run build
```

<!-- 5. Install the plugin into the lite-explorer by running the following command _while inside ethereum-lite-explorer_ :

```javascript
$ cd ..
$ acp install ./pay-no-load
``` -->

6. Now, inside the file `config.dev.json`, add the module and page definations for loading the module :

Adding the plugin :

```json
"plugins": {
...
    "plugin://aleth.io/eth-common": {
    },
    "plugin://aleth.io/payts": {}
...},
```

Adding the page definition :

```json
{
  "def": "page://aleth.io/payts/profile-page",
  "children": {
    "content": [{ "def": "module://aleth.io/payts/profile" }]
  }
}
```

<!-- Adding icon to the homepage :

```json
{...
"def": "page://aleth.io/dashboard",
"children": {
    "content": [
        { "def": "module://aleth.io/search" },
        { "def" : "module://aleth.io/pay-no-load/home-link" }, ...
``` -->

## Features

---

### Displays:

#### 1. token contract metadata (i.e. total supply, symbol, decimals, etc.)

<img src="./src/gifs/Token-Contract-Details.gif" alt="Show Token Contract Details" style="width:70%; margin-left: auto; margin-right: auto; display: block">

#### 2. all token balances for a given wallet address

<img src="./src/gifs/Ethereum-Lite-Blockchain-Explorer-Account-Token-Balance.gif" style="width:70%; margin-left: auto; margin-right: auto; display: block">

#### 3. latest transactions from/to a contract address

<img src="./src/gifs/Transaction-Decoding.gif" alt="Decode Txn from latest" style="width:70%; margin-left: auto; margin-right: auto; display: block">

#### 4. _decoded payloads (parameters/arguments) of transactions_ [most IMPORTANT feature; hence the repo name ;-)]

<hr />

<p align="center">Made with ❤️ by <a href="https://www.linkedin.com/in/smit-r-417517139/">Smit Rajput</a> • <a href="https://www.linkedin.com/in/akash981/"> Akash</a> • <a href="https://www.linkedin.com/in/tezan-sahu-a85802163/">Tezan Sahu</a> </a>
