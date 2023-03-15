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
The 'admin.startRPC' command in Ethereum is used to start an RPC (Remote Procedure Call) server on the node, which allows remote clients to interact with the node over the network.It is typed as admin.startRPC(port, host, cors, apis)<br>
Here,<br>
'port' argument specifies the TCP port number on which the RPC server should listen for incoming connections<br>
'host' argument specifies the IP address or hostname of the network interface on which the RPC server should listen<br>
'cors' argument specifies a list of allowed CORS (Cross-Origin Resource Sharing) domains<br>
'apis' argument specifies a list of available APIs (Application Programming Interfaces) for the RPC server<br>


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







## miner.

<br><br>
