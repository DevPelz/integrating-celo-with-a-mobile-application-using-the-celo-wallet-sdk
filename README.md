# Integrating Celo with a mobile application using the Celo Wallet SDK

## Table of Content
- [Integrating Celo with a mobile application using the Celo Wallet SDK](#integrating-celo-with-a-mobile-application-using-the-celo-wallet-sdk)
  - [Table of Content](#table-of-content)
  - [Introduction](#introduction)
  - [Requirements](#requirements)
  - [What Is Celo?](#what-is-celo)
  - [What Is the Celo SDK?](#what-is-the-celo-sdk)
  - [Part 1: Setting up the Development Environment](#part-1-setting-up-the-development-environment)
    - [Step 1: Install the Celo Wallet SDK](#step-1-install-the-celo-wallet-sdk) 
    - [Step 2: Creating a Celo Account](#step-2-creating-a-celo-account)
  - [Part 2: Interacting With the Celo Blockchain](#part-2-interacting-with-the-celo-blockchain)
    - [Sending Transactions](#sending-transactions)
    - [Receiving a Transaction](#receiving-a-transaction)
  - [Part 3: Building a Mobile App with Celo Wallet SDK](#part-3-building-a-mobile-app-with-celo-wallet-sdk)
  - [Part 4: Implementing Celo Functionality in Your Mobile Application](#part-4-implementing-celo-functionality-in-your-mobile-application)
    - [Step 1: Integrate the Celo Wallet SDK into Your Mobile Application](#step-1-integrate-the-celo-wallet-sdk-into-your-mobile-application)
    - [Step 2: Add Authentication Functionality](#step-2-add-authentication-functionality)
  - [Part 5: Sending and Recieving Celo Tokens](#part-5-sending-and-recieving-celo-tokens)
  - [Part 6: Building the Mobile Application](#part-6-building-the-mobile-application)
    - [Step 1: Configure the React Native Environment](#step-1-configure-the-react-native-environment)
    - [Step 2: Integrate the Celo Wallet SDK into the Mobile Application](#step-2-integrate-the-celo-wallet-sdk-into-the-mobile-application)
    - [Step 3: Adding Screens](#step-3-adding-screens)
  - [Conclusion](#conclusion)

## Introduction
In this article, you will learn about the following concepts:
- The Celo blockchain
- The Celo wallet
- How to build a mobile app using react native
- How to create and integrate Celo to a conntract using the Celo Wallet SDK.

## Requirements
Here are some of the basic requirements for you to integrate Celo with a mobile application using the Celo Wallet SDK:

- Solidity
- JavaScript
- Smart contracts and blockchain principles
- Basic knowledge of mobile application development
- Knowledge of the React Native framework
- Celo Wallet SDK: You will need to download and install the Celo Wallet SDK on your machine.
- Development environment: You will need a development environment set up on your machine.

In addition, you will need to have the following software installed on your development machine:

- Node.js version 14 or higher
- NPM (Node Package Manager) version 6 or higher
- Yarn package manager version 1.22 or higher
- Git version control software

Alright, let's get started.

## What Is Celo?

**[Celo](https://docs.celo.org/general)** is a decentralized, open-source blockchain network that aims to provide people all over the world with accessible and secure financial tools. Because it is based on the Ethereum Virtual Machine (EVM) and is compatible with the Ethereum network, developers can use the same smart contract code on both Celo and Ethereum.

The **[Celo](https://docs.celo.org/general)** blockchain's primary goal is to create a more inclusive financial system by making financial services available to anyone with a smartphone. The platform's goal is to lower the barriers to entry for individuals and small businesses seeking financial services such as remittances, microlending, and savings while maintaining the highest level of security and transparency.

**[Celo](https://docs.celo.org/general)**'s approach to inclusivity includes various design elements that set it apart from other blockchain networks. For example, it uses a unique phone-based identity system to help individuals without traditional forms of identification to access financial services. It also employs a stablecoin, the Celo Dollar (cUSD), to provide a stable store of value and facilitate low-cost transactions across the platform.

**[Celo](https://docs.celo.org/general)** employs a **proof-of-stake** consensus mechanism, allowing users to participate in block validation by securing their cUSD or CELO tokens as collateral. This mechanism ensures that validators have a vested interest in the network's success and that transactions can be processed efficiently and securely.

In summary, the Celo blockchain is intended to provide people all over the world with accessible, secure, and transparent financial services. Its use of mobile-first development, a stablecoin, and a unique identity system all help it to achieve its goal of creating a more inclusive financial system. Its compatibility with the Ethereum network, use of proof-of-stake consensus, and emphasis on security and transparency make it an appealing option for both developers and users.

## What Is the Celo SDK?

The **[Celo SDK](https://celo-sdk-docs.readthedocs.io/en/latest/)** (Software Development Kit) is a collection of developer tools designed to assist developers in creating and integrating financial applications on the Celo blockchain. The SDK includes a comprehensive set of tools and resources that enable developers to build decentralized applications (dApps) that interact with the Celo blockchain and give users access to a variety of financial services. The Celo SDK is intended to make it simple for developers to create and deploy smart contracts on the Celo blockchain. The SDK comes with a collection of pre-built contracts that can be used as templates or customized to fit specific use cases. Stablecoins, lending protocols, and decentralized exchanges can all be created using these contracts.

The **[Celo SDK](https://celo-sdk-docs.readthedocs.io/en/latest/)**  also includes a set of development tools that make it simple for developers to write, test, and deploy smart contracts. These tools include a command-line interface (CLI) for interacting with the Celo blockchain, a testing framework for testing smart contracts, and an integrated development environment (IDE) for writing and debugging smart contracts.

In addition to smart contract development tools, the **[Celo SDK](https://celo-sdk-docs.readthedocs.io/en/latest/)**  includes a set of APIs that developers can use to integrate their applications with the Celo blockchain. These APIs enable developers to access blockchain data such as transaction history and account balances, as well as interact with smart contracts on the blockchain.

The **[Celo SDK](https://celo-sdk-docs.readthedocs.io/en/latest/)** 's emphasis on mobile-first development is one of its distinguishing features. Developers can use the SDK's mobile wallet to integrate financial services directly into their mobile applications. This enables developers to create dApps that are accessible to anyone with a smartphone, increasing the accessibility of financial services to people all over the world.

The **[Celo SDK](https://celo-sdk-docs.readthedocs.io/en/latest/)**  also includes a collection of tools and resources to assist developers in developing and deploying decentralized applications on the Celo network. Documentation, sample code, and a developer community where developers can share knowledge and collaborate on projects are among the resources available.

Putting it all together, the **[Celo SDK](https://celo-sdk-docs.readthedocs.io/en/latest/)**  is a powerful set of tools that gives developers everything they need to build and deploy financial applications on the Celo blockchain. Its emphasis on mobile-first development, a comprehensive set of development tools and resources, and pre-built smart contracts make it an excellent choice for developers looking to create decentralized financial applications on the Celo network.

Now that you've learned what **[Celo](https://docs.celo.org/general)**  and **[Celo SDK](https://celo-sdk-docs.readthedocs.io/en/latest/)** are all about here's a tutorial on how to integrate the Celo with a mobile application using the **[Celo Wallet SDK](https://docs.celo.org/wallet)**

## Part 1: Setting up the Development Environment
  
  The first step in integrating Celo with a mobile application is to set up the development environment. We will be using the React Native framework to create our mobile application, so you will need to have the React Native CLI installed. If you don't have it installed, you can install it by running the following command in your terminal:

  ```bash
  npm install -g react-native-cli
  ```

Once you have the React Native CLI installed, you can create a new React Native project by running the following command:

```bash
react-native init MyCeloApp
```

This will create a new React Native project called MyCeloApp in your current directory. Next, you will need to navigate to the project directory by running the following command:

```bash
cd MyCeloApp
```

Now that you have the basic React Native project set up, you can start integrating Celo with your mobile application by following the steps below. 

### Step 1: Install the Celo Wallet SDK

Installing the **[Celo Wallet SDK](https://docs.celo.org/wallet)**  is the first step in integrating Celo with your mobile application. The SDK is available on NPM as a package that can be installed with the following command:

```bash
npm install @celo/walletkit
```
This will install the Celo Wallet SDK and its dependencies in your project.

### Step 2: Creating a Celo Account

Before we can start sending and receiving transactions on the Celo blockchain, we need to create a Celo account. We can do this using the `@celo/wallet-base` package.

First, we need to import the Wallet class from the `@celo/wallet-base` package:

``` javascript
import { Wallet } from '@celo/wallet-base';
```
Next, we can create a new Celo account by running the following code:

```javascript
const wallet = new Wallet();
const account = await wallet.createAccount();
```

This will create a new Celo account and return the account address. We can use this address to send and receive transactions on the Celo blockchain.

## Part 2: Interacting With the Celo Blockchain

Now that we have created a Celo account, we can start interacting with the Celo blockchain. The `@celo/contractkit` package provides a JavaScript library for interacting with the Celo blockchain, and we can use it to send and receive transactions.

First, we need to import the ContractKit class from the `@celo/contractkit` package:

```javascript
import { ContractKit } from '@celo/contractkit';
```

Next, we can create a new ContractKit instance by running the following code:

```javascript
const contractKit = new ContractKit();
```

This will create a new instance of ContractKit that we can use to interact with the Celo blockchain.

### Sending Transactions

To send a transaction on the Celo blockchain, we need to do the following:

- Get the account's private key
- Create a transaction object
- Sign the transaction with the account's private key
- Send the signed transaction to the Celo blockchain

Here's an example of how we can send a transaction using the `ContractKit` library:

```javascript
import { ContractKit, newKitFromWeb3 } from '@celo/contractkit';
import { newKit } from '@celo/contractkit/lib/kit';
import { Wallet } from '@celo/wallet-base';
import Web3 from 'web3';

const web3 = new Web3('https://forno.celo.org');
const contractKit = newKitFromWeb3(web3);

const privateKey = 'YOUR_PRIVATE_KEY';
const wallet = new Wallet(privateKey);

async function sendTransaction() {
  const account = await wallet.getAccounts()[0];
  const txObject = {
    from: account,
    to: 'YOUR_RECEIVING_ADDRESS',
    value: contractKit.web3.utils.toWei('1', 'ether'),
  };
  const tx = await contractKit.sendTransactionObject(txObject);
  const receipt = await tx.waitReceipt();
  console.log(receipt);
}
```
In this example, we first import the necessary packages, including `ContractKit`, `Wallet`, and `Web3`. We then create a new `Web3` instance pointing to the Celo blockchain's node URL. We create a new `ContractKit` instance from the `Web3` instance and then create a new `Wallet` instance with the account's private key.

In the `sendTransaction` function, we get the first account from the Wallet instance, create a transaction object with the from address, to address, and value of 1 Celo, and send the transaction using the ContractKit instance. We then wait for the transaction receipt and log it to the console.

### Receiving a Transaction

To receive a transaction on the Celo blockchain, we need to do the following:

- Listen for incoming transactions
- Process the incoming transaction

Here's an example of how we can receive transactions using the ContractKit library:

```javascript
import { ContractKit } from '@celo/contractkit';
import { newKitFromWeb3 } from '@celo/contractkit/lib/kit';
import Web3 from 'web3';

const web3 = new Web3('https://forno.celo.org');
const contractKit = newKitFromWeb3(web3);

async function listenForIncomingTransactions() {
  const address = 'YOUR_RECEIVING_ADDRESS';
  const filter = contractKit.web3.eth.filter({ toBlock: 'latest', address });
  filter.watch((error, result) => {
    if (!error) {
      console.log(result);
      // Process the incoming transaction here
    }
  });
}
```
In this example, we first import the necessary packages, including `ContractKit` and `Web3`. We then create a new `Web3` instance pointing to the Celo blockchain's node URL. We create a new `ContractKit` instance from the `Web3` instance.

In the `listenForIncomingTransactions` function, we specify the `address` that we want to listen for incoming transactions on and create a new `filter` using the `Web3` instance. We then watch the `filter` for incoming transactions, and when we receive one, we log it to the console and process it as necessary.

## Part 3: Building a Mobile App with Celo Wallet SDK

We can utilize the Celo Wallet SDK to construct a mobile app that can communicate with the Celo blockchain now that we know how to interact with it using the ContractKit library. In this part, we'll walk through the processes required to create a simple mobile app capable of sending and receiving transactions on the Celo blockchain.

- Creating a new Expo project:
To create a new Expo project, run the following command in your terminal:

```bash
expo init my-celo-app
```

This will create a new Expo project with the name my-celo-app.

- Installing Dependencies:
Next, we need to install the dependencies required for the mobile app. Run the following command in your terminal:

```bash
cd my-celo-app
npm install @celo/dappkit @celo/wallet-base @celo/contractkit react-native-elements
```

This will install the necessary dependencies for the mobile app, including `@celo/dappkit`, `@celo/wallet-base`, `@celo/contractkit`, and `react-native-elements`.

- Setting up the mobile app:
Once the dependencies have been installed, we can start setting up the mobile app.

Open the App.js file in your favorite code editor and add the following code:

```javascript
import React, { useState, useEffect } from 'react';
import { StyleSheet, Text, View, TouchableOpacity } from 'react-native';
import { DappKit } from '@celo/dappkit';
import { Wallet } from '@celo/wallet-base';
import { ContractKit } from '@celo/contractkit';
import { Button, Input } from 'react-native-elements';
import { createStackNavigator } from '@react-navigation/stack';
import { NavigationContainer } from '@react-navigation/native';
import { LoginScreen } from './screens/LoginScreen.js';

const Stack = createStackNavigator();
const contractKit = new ContractKit();
const wallet = new Wallet();

export default function App() {
  const [account, setAccount] = useState('');

  useEffect(() => {
    async function getAccount() {
      const accounts = await wallet.getAccounts();
      setAccount(accounts[0]);
    }
    getAccount();
  }, []);

  const handleSendTransaction = async (toAddress, amount) => {
    const requestId = Math.floor(Math.random() * 1000000);
    const dappkitResponse = await DappKit.sendTransactionRequest(
      contractKit,
      {
        from: account,
        to: toAddress,
        value: amount,
      },
      requestId,
    );
    const status = await dappkitResponse.waitReceipt();
    console.log(status);
  }

  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Login" component={LoginScreen} /> 
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```
Do not worry about some of the imported files that are missing for now, we will create and add relevant updates to the file later on in the tutorial.

## Part 4: Implementing Celo Functionality in Your Mobile Application

Now that you understand the fundamentals of the Celo Wallet SDK and how to interact with the Celo blockchain, it's time to begin incorporating Celo functionality into your mobile application.

### Step 1: Integrate the Celo Wallet SDK into Your Mobile Application

The first step in integrating Celo with your mobile application is to import the Celo Wallet SDK and set up a connection to the Celo network. This can be done using the following code:

```javascript
import { CeloWallet } from '@celo/walletkit';

const celoWallet = new CeloWallet();
celoWallet.connect();
```

This code creates a new instance of the `CeloWallet` class and connects it to the Celo network.

### Step 2: Add Authentication Functionality

The user will need to authenticate their identity using the Celo Wallet SDK before they can interact with the Celo network via your mobile application. This can be accomplished with the following code:

```javascript
const auth = await celoWallet.authenticate();
console.log(auth);
```

This code opens the Celo Wallet app and prompts the user to authenticate their identity. Once the user has authenticated, the code logs an authentication object to the console.

## Part 5: Sending and Recieving Celo Tokens
Now that we have successfully integrated the Celo Wallet SDK into our mobile app, let's take a look at how we can use it to send and receive Celo tokens.

To send Celo tokens, we need to first retrieve the user's account address and balance. We can do this using the `getAccounts` and `getBalances` methods provided by the Celo Wallet SDK. Let's add a button to our app that retrieves this information when clicked:

```javascript
<Button
    android:id="@+id/btn_get_balance"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Get Balance" />
```

```javascript
let btnGetBalance = findViewById<Button>(R.id.btn_get_balance)

btnGetBalance.setOnClickListener {
    let accounts = celoWallet.getAccounts()
    if (accounts.isNotEmpty()) {
        let account = accounts[0]
        let balances = celoWallet.getBalances(account)
        let celoBalance = balances.find { it.tokenInfo.symbol == "CELO" }
        let cUsdBalance = balances.find { it.tokenInfo.symbol == "cUSD" }
        Toast.makeText(this, "CELO balance: ${celoBalance?.balance}, cUSD balance: ${cUsdBalance?.balance}", Toast.LENGTH_SHORT).show()
    } else {
        Toast.makeText(this, "No accounts found.", Toast.LENGTH_SHORT).show()
    }
}
```

When the `Get Balance` button is clicked, we retrieve the user's accounts and balances using the `getAccounts` and `getBalances` methods. We then display the CELO and cUSD balances in a toast message.

Next, let's add a button to our app that allows the user to send Celo tokens to another account:

```javascript
<Button
    android:id="@+id/btn_send_celo"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Send CELO" />
```

```javascript
let btnSendCelo = findViewById<Button>(R.id.btn_send_celo)

btnSendCelo.setOnClickListener {
    let accounts = celoWallet.getAccounts()
    if (accounts.isNotEmpty()) {
        let account = accounts[0]
        let intent = celoWallet.getSendIntent(account, "0x2D0f8175f5E86C7fBB98b3Ee7EAD35Fa2Cfc32aC", "1")
        startActivityForResult(intent, CeloWallet.SESSION_REQUEST_CODE)
    } else {
        Toast.makeText(this, "No accounts found.", Toast.LENGTH_SHORT).show()
    }
}
```
When the `Send CELO` button is clicked, we retrieve the user's accounts using the `getAccounts` method. We then create a send intent using the `getSendIntent` method, passing in the recipient address and the amount to send. Finally, we start the send session using the `startActivityForResult` method, passing in the send intent and the session request code.

You will need to install the qrcode library to generate QR codes. You can install it using npm with the following command:

```bash
npm install qrcode
```

Futhermore to receive Celo tokens, we need to create a QR code that contains the user's account address. We can do this using the `generateQrCode` method provided by the Celo Wallet SDK. Let's add a button to our app that generates this QR code:

```javascript
import QRCode from 'qrcode';

<Button
    android:id="@+id/btn_generate_qr_code"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Generate QR Code" />

async function generateQRCode() {
  const requestId = Math.floor(Math.random() * 1000000);
  const dappkitResponse = await DappKit.waitForAccountAuth(contractKit, requestId);
  const address = dappkitResponse.address;

  QRCode.toDataURL(address, function (err, url) {
    if (err) console.log('error generating QR code');
    else {
      setQRCode(url);
      setStep(3);
    }
  });
}
```

## Part 6: Building the Mobile Application

Now that we've finished the server-side functionality, it's time to start working on our mobile app. In this article, we'll use React Native to build a cross-platform mobile app that works with the Celo Wallet SDK.

### Step 1: Configure the React Native Environment

Before we begin, ensure that you have React Native CLI and Node.js installed on your machine.

To create a new React Native project, open your terminal and enter the following command:

```bash
npx react-native init celoWalletIntegration
```

This will create a new React Native project with the name `celoWalletIntegration`. Now navigate to the project directory using the following command:

```bash
cd celoWalletIntegration
```

### Step 2: Integrate the Celo Wallet SDK into the Mobile Application

To include the Celo Wallet SDK in our mobile application, we must use npm to install the `@celo-tools/celo-identity-wallet` package.

In your terminal, type the following command:

```bash
npm install @celo-tools/celo-identity-wallet --save
```

### Step 3: Adding Screens

Now, we will create two screens for our mobile application: a home screen and a login screen.

Create a new folder named `screens` in the root directory of your project. Inside this folder, create two new files: `HomeScreen.js` and `LoginScreen.js`.

Add the following code to `HomeScreen.js`:

```javascript
import React, { useState } from 'react';
import { View, Text, StyleSheet } from 'react-native';
import { CeloWallet } from '@celo-tools/celo-identity-wallet';

const HomeScreen = () => {
  const [account, setAccount] = useState(null);

  const connectWallet = async () => {
    const celoWallet = new CeloWallet();
    await celoWallet.createAccount();
    const account = await celoWallet.getAccounts();
    setAccount(account[0]);
  };

  return (
    <View style={styles.container}>
      <Text style={styles.title}>Welcome to Celo Wallet Integration!</Text>
      {account ? (
        <Text style={styles.subtitle}>Your account: {account}</Text>
      ) : (
        <Text style={styles.subtitle}>Please connect your Celo wallet</Text>
      )}
      <TouchableOpacity style={styles.button} onPress={connectWallet}>
        <Text style={styles.buttonText}>Connect Wallet</Text>
      </TouchableOpacity>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    backgroundColor: '#fff',
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 10,
  },
  subtitle: {
    fontSize: 16,
    marginBottom: 20,
  },
  button: {
    backgroundColor: '#1E88E5',
    padding: 10,
    borderRadius: 5,
  },
  buttonText: {
    color: '#fff',
    fontWeight: 'bold',
  },
});

export default HomeScreen;
```

This code creates a functional component that displays a welcome message and a button to connect the Celo wallet. The `CeloWallet` class from the `@celo-tools/celo-identity-wallet` package is used to create and manage the wallet.

Next you should add the following code to `LoginScreen.js`:

```javascript
import React, { useState } from 'react';
import { View, StyleSheet } from 'react-native';
import { Input, Button } from 'react-native-elements';
import { Wallet } from '@celo/wallet-base';

const wallet = new Wallet();

const LoginScreen = ({ navigation }) => {
  const [phoneNumber, setPhoneNumber] = useState('');
  const [pin, setPin] = useState('');

  async function handleLogin() {
    const [phoneNumberHash, salt] = await wallet.getPhoneNumberIdentifier(
      phoneNumber,
    );
    navigation.navigate('Verification', {
      phoneNumberHash,
      salt,
      pin,
    });
  }

  return (
    <View style={styles.container}>
      <Input
        placeholder="Phone number"
        keyboardType="phone-pad"
        onChangeText={setPhoneNumber}
        value={phoneNumber}
        leftIcon={{ type: 'font-awesome', name: 'phone' }}
      />
      <Input
        placeholder="PIN"
        keyboardType="number-pad"
        onChangeText={setPin}
        value={pin}
        leftIcon={{ type: 'font-awesome', name: 'lock' }}
        secureTextEntry={true}
      />
      <Button title="Log In" onPress={handleLogin} />
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    padding: 20,
  },
});

export default LoginScreen;
```

In addition Create a `TransactionScreen.js` file in the `screens` folder with the following code:

```javascript
import React, { useState } from 'react';
import { View, Text, TextInput, StyleSheet } from 'react-native';
import { Button } from 'react-native-elements';
import QRCode from 'react-native-qrcode-svg';
import { DappKit } from '@celo/dappkit';
import { ContractKit } from '@celo/contractkit';
import { walletLink } from '../utils/walletLink';

const contractKit = new ContractKit();

export default function TransactionScreen({ navigation }) {
  const [toAddress, setToAddress] = useState('');
  const [amount, setAmount] = useState('');

  async function sendTransaction() {
    const requestId = Math.floor(Math.random() * 1000000);
    const dappkitResponse = await DappKit.sendTransactionRequest(
      contractKit,
      {
        from: walletLink.address,
        to: toAddress,
        value: amount,
      },
      requestId,
    );
    const status = await dappkitResponse.waitReceipt();
    console.log(status);
    navigation.navigate('Home');
  }

  return (
    <View style={styles.container}>
      <View style={styles.qrContainer}>
        <QRCode value={walletLink.publicAddress} size={200} />
      </View>
      <View style={styles.inputContainer}>
        <TextInput
          style={styles.input}
          placeholder="Recipient Address"
          value={toAddress}
          onChangeText={setToAddress}
        />
        <TextInput
          style={styles.input}
          placeholder="Amount (CELO)"
          value={amount}
          onChangeText={setAmount}
        />
      </View>
      <Button title="Send" onPress={sendTransaction} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  qrContainer: {
    padding: 20,
    alignItems: 'center',
  },
  inputContainer: {
    marginTop: 50,
    width: '80%',
  },
  input: {
    borderBottomWidth: 1,
    borderColor: '#ccc',
    padding: 10,
    marginBottom: 20,
  },
});
```
Next we update the `App.js` file with the following code :

``` javascript
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';
import { createStackNavigator } from '@react-navigation/stack';
import { NavigationContainer } from '@react-navigation/native';
import { HomeScreen } from './screens/HomeScreen.js';
import { LoginScreen } from './screens/LoginScreen.js';
import {TransactionScreen} from './screens/TransactionScreen.js';

const Stack = createStackNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Login" component={LoginScreen} />
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Transaction" component={TransactionScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

Start the application by running `expo start` in the terminal, follow the prompts in the app to connect your wallet to the mobile ap and to approve the transactions.

Congratulations!! You have successfully built a mobile app and integrated celo into your mobile app using the Celo SDK. Now, you can interact with your app perfectly.


## Conclusion

In this lesson, we learned how to use the **Celo Wallet SDK** to integrate Celo with a mobile application. We began by configuring our development environment and installing the required packages. Then, to allow users to verify themselves, we constructed a basic login screen and connected it to the **Celo Wallet SDK**. We also added the ability for users to submit and receive Celo transactions via the Celo Contract Kit.

By the end of the course, we had created a working mobile application that makes use of Celo's blockchain technology. This opens up a world of possibilities for developers aiming to create secure, quick, and cost-effective decentralized applications.

In general, the **Celo Wallet SDK** offers programmers a straightforward and user-friendly method of incorporating Celo's blockchain technology into their mobile applications. Developers may easily and quickly design decentralized applications with its robust collection of tools and functionalities. We sincerely hope that this guide has been useful in introducing you to Celo and the **Celo Wallet SDK**.