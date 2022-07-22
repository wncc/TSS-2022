# **Brownie** 
What is a Brownie?
It's a small rectangular sweet confectionary item loved by everyone, jk!
</br>


Brownie we are talking about today is a Python-based framework to develop and test smart contracts. 
</br>
</br>
_Okay, but why use Brownie?_

- Deployment: Automate the deployment of many contracts onto the blockchain, and any transactions needed to initialize or integrate them.
- Interaction: Write scripts or use the console to interact with your contracts on the mainnet, or for quick testing in a local environment.
- Debugging: Get detailed information when a transaction reverts, to help you pinpoint the issue quickly.
- Testing: Write unit tests in python and evaluate test coverage based on stack trace analysis. We make no promises.

Remix IDE was good to start with but as we build more complex smart contracts frameworks like Brownie come real handy.





To install Brownie and Ganache CLI follow the instructions given [here](https://iamdefinitelyahuman.medium.com/getting-started-with-brownie-part-1-9b2181f4cb99)



There are two ways to start a project in brownie:

>- Create an empty project using ``brownie init``.
>- Create a project from an existing template using ``brownie bake``.

Read [this](https://betterprogramming.pub/getting-started-with-brownie-part-2-615a1eec167f) article about getting started with Brownie

Now that you have created a project in a Brownie, open the project in any code editor like VS code where you can work on your project and manage  it properly.

You may write your smart contracts in a similar fashion as we did  on Remix IDE i.e. create contracts with .sol extension in the contracts section of your project.

Now let's see how to compile them!



## Compiling contracts
 Use the command - ```brownie compile ``` to compile all the contracts in the contracts folder. 
 It is to be noted that Brownie doesnt not recompile all the contracts,  if no changes have been made in some of the contracts they wont be recompiled, in case you still want to force recompile all the contracts , use the command - ``` brownie compile --all```.

 If one or more contracts are unable to compile, Brownie raises an exception with information about why the compilation failed. You cannot use Brownie with a project as long as compilation is failing. You can temporarily exclude a file or folder from compilation by adding an underscore ``(_)`` to the start of the name.


> NOTE - Brownie supports Solidity versions ```>=0.4.22 ```.

You may refer [this](https://youtu.be/NAtYl742SQo) YT tutorial as well.

## Interacting with your Contracts

Brownie has three main components that you can use while developing your project:


> - Scripts allow you to automate common tasks and handle deployments.
> - Tests help to ensure that your contracts are executing as intended.
> - The console is useful for quick testing and debugging.




##   Working with Scripts
Using ETH Brownie you may also automate contract deployment and interactions by writing scripts. To do so, you need to place ‘from brownie import *’ at the beginning of your particular script. On top of that, you must store the script in the ‘script/’ folder. 
 Watch [this](https://youtu.be/lJd8-TLpAtY) tutorial!




 ## Writing Tests for our Contracts
 Brownie uses the [pytest](https://docs.pytest.org/en/7.1.x/) framework to test contracts.
 Brownie testing offers many fixtures, an option to handle reverted transactions, isolating tests, and more.
 You definitely need to run tests before deploying your contract on the actual blockchain as once deployed it can't be changed!

 Watch [this](https://youtu.be/uR3VKVQtYhQ) detailed tutorial on testing with Brownie!
 

## Using the Console

The Brownie console is very useful. Especially, when programmers want to interact with smart contracts deployed on a non-local chain. Aside from interaction, the console is great for development and quick testing. Luckily for those familiar with Python, the console feels very similar to a regular Python interpreter. 




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

 














