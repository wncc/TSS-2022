# **Brownie** 
What is a Brownie?
It's a small rectangular sweet confectionary item loved by everyone, jk!
</br>

Brownie we are talking about today is a Python-based framework to develop and test smart contracts. 
</br>
</br>
_Okay, but why use Brownie?_

>- Deployment: Automate the deployment of many contracts onto the blockchain, and any transactions needed to initialize or integrate them.
>- Interaction: Write scripts or use the console to interact with your contracts on the mainnet, or for quick testing in a local environment.
>- Debugging: Get detailed information when a transaction reverts, to help you pinpoint the issue quickly.
>- Testing: Write unit tests in python and evaluate test coverage based on stack trace analysis. We make no promises.




To install Brownie and Ganache CLI follow the instructions given [here](https://iamdefinitelyahuman.medium.com/getting-started-with-brownie-part-1-9b2181f4cb99)



There are two ways to start a project in brownie:

>- Create an empty project using ``brownie init``.
>- Create a project from an existing template using ``brownie bake``.

Read [this](https://betterprogramming.pub/getting-started-with-brownie-part-2-615a1eec167f) article about getting started with Brownie


## **Compiling contracts**
 Use the command - ```brownie compile ``` to compile all the contracts in the contracts folder. 
 It is to be noted that Brownie doesnt not recompile all the contracts,  if no changes have been made in some of the contracts they wont be recompiled, in case you still want to force recompile all the contracts , use the command - ``` brownie compile --all```.

 If one or more contracts are unable to compile, Brownie raises an exception with information about why the compilation failed. You cannot use Brownie with a project as long as compilation is failing. You can temporarily exclude a file or folder from compilation by adding an underscore ``(_)`` to the start of the name.


> NOTE - Brownie supports Solidity versions ```>=0.4.22 ```.


// 
.. 
// 

## **Interacting with your Contracts**

Brownie has three main components that you can use while developing your project:

> - The console is useful for quick testing and debugging.
> - Scripts allow you to automate common tasks and handle deployments.
> - Tests help to ensure that your contracts are executing as intended.

Clearly you dont get these functionalities in the  online Remix compiler (which is great to get started), hence we are learning Brownie!


//


##   Working with Scripts
 Watch [this](https://youtu.be/lJd8-TLpAtY) tutorial.




 ## Writting Tests for our Contracts

 Watch [this](https://youtu.be/uR3VKVQtYhQ) detailed tutorial on testing with Brownie!
 

## Using the Console

From inside a project directory, load it by typing:

    $ brownie console

Brownie will compile the contracts, launch or attach to the local test environment, and then give you a command prompt.

To exit the console use the following command:

    exit()

Use the following command to see available methods and attributes for any class:

    dir()


The following command accepts any object as an argument and displays documentation for the object.

    help()

With these two functions and some curiosity, you can pretty much figure out how to do anything without reaching for the documentation. But do check the [documentation](https://eth-brownie.readthedocs.io/en/stable/toctree.html) in case of confusion.

Do play around with these!!


Let's try doing a couple of things using console.

## Transfering Ether

Since we are using Ganache we already have some accounts with test ether in them. we can look at them by following command in console:

    accounts

Let's transfer 1 ether  form ```account[0]``` to ```account[3]```.


    account[0].transfer(account[3], "1 ether")

> Note: If you dont explicity mention ether , 1 wei will get transfered instead , which is the smallest unit of ether.


We'll be able to see that Ganache mines the transaction immediately, and the result is outputted to the console.

In the last line you must be seeing a ```<Transaction .. ..> ``` like thing, that represents our transcactions, we can look all of these by simply using the command given below:

    history

## Working with contracts 

Let's start with the deployment in console.
</br>
To deploy, we'll use ```.deploy()``` function, thou you have to put in certain attributes to deploy and be able to see it in transaction history.
</br>
Example:

    contract_name.deploy({'from':account[3]})

So, we deployed our contract called ```contract_name``` from an account indexed 3.

</br>
Check your history your deployment will be reflected!

> Note: If you use the function ``` .deploy ``` without any attributes it will not be reflected in the history.
</br>

Now if you push your contract name in the console you will see a list of contracts deployed. For example in our case it will contain only one transaction ID as we deployed only one contract using account indexed 3.

 






