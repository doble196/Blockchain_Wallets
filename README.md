# Blockchain_Wallets  

`Instructions`
The steps for this contract are broken out into the following sections:  

## The steps for this application are divided into the following sections:  

   * Import Ethereum Transaction Functions into the Fintech Finder Application  

   * Sign and Execute a Payment Transaction.  

   * Inspect the Transaction on Ganache.  

   * Add Relevant User Inputs to the Streamlit Interface.  

#### Add your mnemonic seed phrase (provided by Ganache) to the starter code’s SAMPLE.env file. Rename the file .env.  


## Step 1: Import Ethereum Transaction Functions into the Fintech Finder Application:  

In this section, you'll import several functions from the crypto_wallet.py script into the file fintech_finder.py, which contains code for Fintech Finder’s customer interface, in order to add wallet operations to the application. For this section, you will assume the perspective of a Fintech Finder customer (i.e., you’ll provide your Ethereum wallet and account information to the application).  

`Complete the following steps:`  

   * Review the code contained in the crypto_wallet.py script file. Note that the Ethereum transaction functions that you have built throughout this module—including wallet, wallet.derive_acount, get_balance, fromWei, estimateGas, sendRawTransaction, and others—have now been incorporated into Python functions that allow you to automate the process of accessing them.    

   * Add your mnemonic seed phrase (provided by Ganache) to the starter code’s SAMPLE.env file. When the information has been added, rename the file .env.  

   * Open the fintech_finder.py file. Toward the top of the file, after the import statements that are provided, import the following functions from the crypto_wallet.py file:  

       * generate_account.  

       * get_balance.  

       * send_transaction.  

       * Within the Streamlit sidebar section of code, create a variable named account. Set this variable equal to a call on the generate_account function. This function will create the Fintech Finder customer’s (in this case, your) HD wallet and Ethereum account.  

       * Within this same section of the fintech_finder.py file, define a new st.sidebar.write function that will display the balance of the customer’s account. Inside this function, call the get_balance function and pass it your Ethereum account.address.  


## Step 2: Sign and Execute a Payment Transaction  
Next, you'll write the code that will calculate a fintech professional’s wage, in ether, based on the worker’s hourly rate and the number of hours that they work for a customer. (The fintech professionals’ hourly rates are provided in the candidate_database that is found in fintech_finder.py.)  

You will then write code that uses the calculated wage value to send a transaction that pays the worker. This code should allow the Fintech Finder customer to authorize the transaction with their digital signature. For the purpose of testing out this application, you will use your own Ethereum account information as the customer account information.  

`To accomplish all of this, complete the following steps:`  

   * Fintech Finder customers will select a fintech professional from the application interface’s drop-down menu, and then input the amount of time for which they’ll hire the worker. Code the application so that once a customer completes these steps, the application will calculate the amount that the worker will be paid in ether. To do so, complete the following steps:  

   * Write the wage variable to the Streamlit sidebar by using st.sidebar.write.  

   * Now that the application can calculate a candidate’s wage, write the code that will allow a customer (you, in this case) to send an Ethereum blockchain transaction that pays the hired candidate. To accomplish this, locate the code that reads if st.sidebar.button("Send Transaction"). You’ll need to add logic to this if statement that sends the appropriate information to the send_transaction function (which you imported from the crypto_wallet script file). Inside the if statement, add the following functionality:  

        Call the send_transaction function and pass it three parameters: 

           * Your Ethereum account information. (Remember that this account instance was created when the generate_account function was called.) From the account instance, the application will be able to access the account.address information that is needed to populate the from data attribute in the raw transaction.  

           * The candidate_address (which will be created and identified in the sidebar when a customer selects a candidate). This will populate the to data attribute in the raw transaction.  

           * The wage value. This will be passed to the toWei function to determine the wei value of the payment in the raw transaction.  

#### Save the transaction hash that the send_transaction function returns as a variable named transaction_hash, and have it display on the application’s web interface.  


## Step 3: Inspect the Transaction  
Now it's time to put it all together and test the Fintech Finder application with your newly integrated Ethereum wallet. You will send a test transaction by using the application’s web interface, and then look up the resulting transaction in Ganache. To do so, complete the following steps:  

`From your terminal`, navigate to the project folder that contains your .env file and the fintech_finder.py and crypto_wallet.py files. Be sure to activate your Conda dev environment if it is not already active.  

   * To launch the Streamlit application, type streamlit run fintech_finder.py.  

   * On the resulting webpage, select a candidate that you would like to hire from the appropriate drop-down menu. Then, enter the number of hours that you would like to hire them for. (Remember, you do not have a lot of ether in your account, so you cannot hire them for long!)  

   * Click the Send Transaction button to sign and send the transaction with your Ethereum account information. Navigate to the Transactions section of Ganache.  

   * Launch Ganashe and see the transaction is validated under transaction details along with history and changes is appropriate wallets.  


## Step 4: Add Relevant User Inputs to the Streamlit Interface
Code additional input areas for the user interface of your Streamlit application. Create these input areas to capture the sender, receiver, and amount for each transaction that you’ll store in the Block record. To do so, complete the following steps:  

   * Delete the input_data variable from the Streamlit interface.  

   * Add an input area where you can get a value for sender from the user.  

   * Add an input area where you can get a value for receiver from the user.  

   * Add an input area where you can get a value for amount from the user.  



### *First transaction running shows `Wage Calculation`:* 

![WageCalculation](ImagesPNG/wage_calculation.png)  
 

### *Transaction hash mined creating `Validated Hash`:* 

![ValidatedHash](ImagesPNG/valideted_txn_hash.png) 


### *Third link in chain `Transaction List`:* 

![TransactionList](ImagesPNG/transactions.png)  


### *Customer sending payment `Transaction Hash` from Ganashe:* 

![TransactionHash](ImagesPNG/transaction_hash.png)  


### *Successful transactions for `BlockchainWallets` from the `streamlit` app:* 

![StreamlitApp](ImagesPNG/succesful.png)  


### *This is the `Ganashe Interface ` block transactions:* 

![BlocksGanashe](ImagesPNG/blocks.png)  


* `Added 9 employees accounts` to the application.  

* `Added` the `extra slots` for `images`.  

* `Ganashe` was `optimized` with a `512bit mnemonic`.  

* `Ganashe test accounts` started with `1000 eth in wallet each`.  

* `Application` is `optimized` to `serve more employees`.  


## Contributor

`Rensley Ramos` - ranly196@gmail.com, https://www.linkedin.com/in/rensley-2-nfty/  