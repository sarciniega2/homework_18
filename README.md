# homework_18
Hello everyone, this file will go over how to use and manage the testnetwork blockchain for our organization.

You will begin building two nodes within your BLOCKCHAIN_TOOLS folder on your gitbash/terminal and the process should look like the picture below:
![Node](StepOne.png)

Make sure to save the Keystore file and the public key adress for both nodes. 

Next, you will use the "./puppeth command on the gitbash/terminal to Configure a new genesis block. Your terminal/gitbash should look like the picture below:
![Puppeth](StepTwo.png)

Your second step will require you to create a network name to administer. 

In this section make sure to select 
* "2. Configure new genesis"  
* "1. Create new genesis from scratch"
* "2. Clique - proof-of-authority"

In the section that poses the question "Which accounts should be pre-funded?", make sure to use the public address information that you saved from the node1 folder to ensure the account is prefunded. Do the same for node2 and skip over the next "0x".

Type "no" for the "Should the precompile- adressess ne pre-funded with 1 wei?"

In the final question for this section, make sure to specify your chain/network ID.

Now select the "Manage existing genesis" and follow this step with the "Export genesis configurations" option. 

Hit enter for the "Which folder to save the genesis specs into". Next, click control C. 

Now you will use a geth command. The command is ./geth init testnetwork1.json --datadir node1 (This is initializing the node). Do the same for node2. Your terminal/gitbash should look something like the picture below. 
![Initialize](StepThree.png)

In this section you will now need to keep two terminals open. 
* In the first terminal the geth command is .geth/ --datadir node1 --mine --miner.threads 1. Make sure to copy the enode link that is populated once the mining for the first node commences. The command and enode will look like the picture below.
![Enable Mining](StepFour.png)

* In the second terminal the geth command will be ./geth --datadir node2 --port 30304 --rpc --bootnodes " " <- paste the enode link from the first terminal into the quotes. 

Now both terminals should be mining which is a success!

Now that you have enabled mining, you will open up MyCrypto and create a custom node by selecting "Change Network". Make sure to use the network name and the ChainID that you created at the begining. The window will look like the picture below.
![Set Up Your Custom Node](Create_Custom.png)

In the next section you will proceed to the KeyStore File option in between "Private Key" and "Mnemonic Phrase". You will select the Keystore File in your folder in the BLOCKCHAIN_TOOLS and type in the password created at the begining. The page will look like the picture below. 
![KeyStoreFile](KeyStoreFile.png)


In the "To Address" section at the top of the page paste your public address key that you sealed at the begining in the terminal. Now click "send transaction". Copy the hash.

Go to "TX Status", paste the hash and wait until your transaction is successful. The page will look like the picture at the bottom. 
![Transaction](Pending_Transaction.png)
