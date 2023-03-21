# Geth Console Commands

## eth.

### eth.accounts
This command returns all the public keys of the existing accounts in the blockchain. Example:

```
eth.accounts
```
<br>

### eth.coinbase

<br>

### eth.call

<br>

### eth.getBalance()
This command returns the balance of a specific account. It is typed as ```eth.getBalance("public_key_of_the_account")``` Example:

```
eth.getBalance("0xe4e557bc95ad7bc81c458746a67e019125c5afb0")
```
After running this command the console will return the balance of this account ```0xe4e557bc95ad7bc81c458746a67e019125c5afb0``` which is the public key of the account.
<br><br>

## personal.
### personal._requestManager

The personal._requestManager code appears to be related to the Ethereum blockchain platform and its web3.py library. The personal object is part of the web3.py library and provides a set of methods for interacting with the Ethereum personal API, which allows users to manage their Ethereum accounts and sign transactions.

The _requestManager attribute is used internally by the web3.py library to manage JSON-RPC requests to the Ethereum node. It is not typically used directly by developers, but is instead accessed through higher-level methods provided by the web3.py library.example: <br>

```
const Web3 = require('web3');
const web3 = new Web3('https://mainnet.infura.io/v3/your-project-id');

const accountAddress = '0x1234567890123456789012345678901234567890';
const accountPassword = 'your-account-password';
const message = 'hello world';

// Use personal._requestManager to call personal_sign method
web3.eth.personal._requestManager.request('personal_sign', [message, accountAddress, accountPassword])
  .then(signedMessage => {
    console.log(signedMessage);
  })
  .catch(error => {
    console.error(error);
  });
```
here,<br>
In this example, we create a Web3 instance with a connection to the Ethereum mainnet using Infura as the provider. We then specify an Ethereum account address and password, and a message that we want to sign.

We use the personal._requestManager attribute to call the personal_sign method, passing in the message, account address, and password as parameters. The _requestManager object handles the JSON-RPC request to the Ethereum node and returns a Promise that resolves with the signed message.

Finally, we log the signed message to the console if the Promise resolves successfully, or log any errors if the Promise rejects. Note that this is just an example, and the specific usage of the personal._requestManager attribute may vary depending on your specific needs and requirements.


<br><br>
### personal.getListWallets

The personal.getListWallets method is a function provided by the personal module in web3.py that returns a list of Ethereum account addresses that are managed by the connected node's wallet.

```
const Web3 = require('web3');
const web3 = new Web3('https://mainnet.infura.io/v3/your-project-id');

// Use personal.getListWallets to get a list of wallet addresses
web3.eth.personal.getListWallets()
  .then(walletAddresses => {
    console.log(walletAddresses);
  })
  .catch(error => {
    console.error(error);
  });
```

here,<br>
In this example, we create a Web3 instance with a connection to the Ethereum mainnet using Infura as the provider. We then use the personal.getListWallets method to get a list of Ethereum account addresses that are managed by the connected node's wallet.

The getListWallets method returns a Promise, which resolves with the list of wallet addresses if the method call is successful. We use the .then() method to handle the successful resolution of the Promise, and log the list of wallet addresses to the console.

If an error occurs during the method call, the Promise will be rejected and we use the .catch() method to handle the error and log it to the console.

Note that this is just an example, and the specific usage of personal.getListWallets may vary depending on your specific needs and requirements.
<br><br>

### personal.newAccount

The personal.newAccount method is a function provided by the personal module in web3.py that creates a new Ethereum account with a specified password.
```
const Web3 = require('web3');
const web3 = new Web3('https://mainnet.infura.io/v3/your-project-id');

// Use personal.newAccount to create a new Ethereum account with a password
web3.eth.personal.newAccount('your-new-account-password')
  .then(newAccount => {
    console.log(newAccount);
  })
  .catch(error => {
    console.error(error);
  });
```
here,<br>
In this example, we create a Web3 instance with a connection to the Ethereum mainnet using Infura as the provider. We then use the personal.newAccount method to create a new Ethereum account with a specified password.

The newAccount method returns a Promise, which resolves with the address of the new account that was created if the method call is successful. We use the .then() method to handle the successful resolution of the Promise, and log the address of the new account to the console.

If an error occurs during the method call, the Promise will be rejected and we use the .catch() method to handle the error and log it to the console.

Note that this is just an example, and the specific usage of personal.newAccount may vary depending on your specific needs and requirements. Additionally, you should be careful when creating new accounts, as they can be a security risk if not properly secured.
<br><br>

<br><br>

## admin.

### admin.addPeer
This command is used in the Geth client for Ethereum to manually add a new peer to a node's list of trusted peers. It is typed as ```admin.addPeer("enode://<peer-enode-info>@<peer-ip-address>:<peer-port>")``` Example:

```
admin.addPeer("enode://1a2b3c4d5e6f7g8h9i0j1k2l3m4n5o6p7q8r9s0t1u2v3w4x5y6z@192.168.0.100:30303")
```
Here,<br>
```enode://1a2b3c4d5e6f7g8h9i0j1k2l3m4n5o6p7q8r9s0t1u2v3w4x5y6z@192.168.0.100:30303``` is the argument to the addPeer command, which is a string representing the enode URL of the peer to be added.

```1a2b3c4d5e6f7g8h9i0j1k2l3m4n5o6p7q8r9s0t1u2v3w4x5y6z``` is a placeholder for the enode information of the peer, which consists of the node's public key and other identifying information. This information is used by the node to establish a direct connection with the peer.

```192.168.0.100``` is the IP address of the peer.

```30303``` is the port number of the peer's Ethereum network interface
<br><br>

### admin.importChain
The 'admin.importChain' command is used in Ethereum to import a previously exported blockchain data file into a new node.Example
```
admin.importChain("/home/user/exported_data/mychaindata.zip")
```
Here <br>
```/home/user/exported_data/mychaindata.zip```  is the argument to the importChain command, which is a string representing the file path of the exported blockchain data file.
The file should be in the .zip format.
<br><br>

### admin.startRPC
The 'admin.startRPC' command in Ethereum is used to start an RPC (Remote Procedure Call) server on the node, which allows remote clients to interact with the node over the network.It is typed as ```admin.startRPC(port, host, cors, apis)```<br>
Here,<br>
```port``` argument specifies the TCP port number on which the RPC server should listen for incoming connections<br>
```host``` argument specifies the IP address or hostname of the network interface on which the RPC server should listen<br>
```cors``` argument specifies a list of allowed CORS (Cross-Origin Resource Sharing) domains<br>
```apis``` argument specifies a list of available APIs (Application Programming Interfaces) for the RPC server<br>


Example:
```
admin.startRPC(8545, "0.0.0.0", "*", ["eth", "net"])
```
<br><br>

### admin.isPrototypeOf
The 'admin.isPrototypeOf' method is used in the JavaScript implementation of the Ethereum client to determine if a given object is an instance of the admin object or one of its prototypes.Example

```var myObject = {}
console.log(admin.isPrototypeOf(myObject)); // Output: false

function MyContract() {}
MyContract.prototype = Object.create(admin);
var myContract = new MyContract();
console.log(admin.isPrototypeOf(myContract)); // Output: true
```

Here,<br>
```var myObject = {}```   This creates a new JavaScript object called myObject using object literal notation.<br>

```console.log(admin.isPrototypeOf(myObject));```   This calls the admin.isPrototypeOf() method to check if the admin object is a prototype of myObject. Since myObject is not an instance of admin or one of its prototypes, the method returns false.<br>

```function MyContract() {}```  This declares a new constructor function called MyContract.<br>

```MyContract.prototype = Object.create(admin);```   This sets the prototype property of MyContract to a new object created by calling Object.create() with admin as its argument. This sets up the prototype chain so that MyContract inherits from admin.<br>

```var myContract = new MyContract();```   This creates a new instance of MyContract called myContract.<br>

```console.log(admin.isPrototypeOf(myContract));```   This calls the admin.isPrototypeOf() method to check if the admin object is a prototype of myContract. Since myContract is an instance of MyContract, which inherits from admin, the method returns true.

<br><br>

### admin.startWS
The 'admin.startWS' method is used in the Ethereum administrative module (admin) to start a WebSocket server that can be used to communicate with a running Ethereum client.Example:
```
admin.startWS(8546, "localhost", "*", ["web3", "net"]);
```
Here,<br>
```8546```  is the port number on which to start the WebSocket server.<br>

```localhost```  is the hostname or IP address on which to listen for incoming connections. If not specified, the server listens on all available network interfaces.<br>

 ```*```                 is a comma-separated list of origins that are allowed to make cross-origin requests to the WebSocket server. If not specified, CORS is disabled.<br>
 
 ```["web3", "net"]```   is an  array of APIs that should be exposed over the WebSocket server. If not specified, all APIs are exposed.<br>
 
 <br><br>
 
 
 ### admin.datadir
 The 'admin.datadir' method is used in the Ethereum administrative module (admin) to retrieve the data directory used by the running Ethereum client.Example:
 
 ```
 console.log(admin.datadir);
 ```
 Here,<br>
The  ```admin.datadir```  method is used to retrieve the data directory used by the Ethereum client. The resulting string is then printed to the console using ```console.log()```.


<br><br>

### admin.nodeInfo

The admin.nodeInfo method is used in the Ethereum administrative module (admin) to retrieve information about the running Ethereum client.Example:

```
console.log(admin.nodeInfo);
```
Here,<br>
```admin.nodeInfo```  method is used to retrieve information about the running Ethereum client. The resulting object is then printed to the console using ```console.log()```

<br><br>







## miner.

<br><br>
