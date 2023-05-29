# Compound-Governance
 The Compound Governance Token (COMP); Holders of this token have the ability to govern the protocol via the governor contract.
 allowance(address,address) :
 This function allows users to check the amount of tokens that have been approved for a particular spender to spend from a particular account. It works by accessing the allowances mapping, which stores the amount of tokens that have been approved for a particular spender to spend from a particular account. The function takes in two parameters, the account address and the spender address, and returns the amount of tokens that have been approved for the spender to spend from the account. (autogenerated documentation)
 approve(address) :
 This function allows a user to approve a spender to spend a certain amount of tokens on their behalf. It takes in two parameters, the address of the spender and the amount of tokens to be approved. The function first checks if the amount is equal to the maximum uint value, and if so, sets the amount to the maximum uint96 value. Otherwise, it uses the safe96 function to ensure that the amount does not exceed 96 bits. The function then sets the allowance for the spender to the specified amount and emits an Approval event. Finally, it returns true. (autogenerated documentation)
 balanceOf(address) :
 This function is used to check the balance of a given account. It takes in an address as an argument and returns the corresponding balance of that account stored in the 'balances' mapping. The 'balances' mapping is a key-value store that maps addresses to their corresponding balances. (autogenerated documentation)
 transfer(address) :
 This function is used to transfer tokens from one address to another. It takes two parameters, an address to send the tokens to and an amount of tokens to send. The function first uses the safe96() function to ensure that the amount of tokens to be sent does not exceed 96 bits. It then calls the _transferTokens() function to transfer the tokens from the sender's address to the destination address. Finally, it returns a boolean value indicating whether the transfer was successful. (autogenerated documentation)
 transferFrom(address,address) :
 This function is used to transfer tokens from one address (src) to another address (dst). The amount of tokens to be transferred is specified by the rawAmount parameter. The function first checks if the sender (spender) is not the same as the source address, and if the spender's allowance is not equal to the maximum value of a uint96. If these conditions are met, the spender's allowance is reduced by the amount of tokens to be transferred. An Approval event is then emitted, and the tokens are transferred from the source address to the destination address. Finally, the function returns true. (autogenerated documentation)
 delegate(address) :
 This function allows a user to delegate their voting rights to another user. It does this by calling the _delegate function, which takes the address of the user delegating their voting rights (msg.sender) and the address of the user they are delegating their voting rights to (delegatee). This allows the delegatee to vote on behalf of the original user. (autogenerated documentation)
 delegateBySig(address,uint8,bytes32,bytes32) :
 This function allows a user to delegate their voting rights to another user by providing a signature. The function first verifies the signature by using the ecrecover function to recover the signatory address from the provided v, r, and s parameters. It then checks that the nonce provided is valid and that the signature has not expired. If all checks pass, the function calls the _delegate function to delegate the voting rights to the delegatee. (autogenerated documentation)
 getCurrentVotes(address) :
 This function is used to retrieve the current number of votes for a given account. It does this by first retrieving the number of checkpoints associated with the account from the numCheckpoints mapping. If the number of checkpoints is greater than 0, it then retrieves the votes from the last checkpoint in the checkpoints mapping associated with the account. If the number of checkpoints is 0, it returns 0. (autogenerated documentation)
 getPriorVotes(address) :
 This function is used to retrieve the number of votes a given account had at a given block number. It does this by using a binary search algorithm to look through the checkpoints array associated with the account. The checkpoints array stores the number of votes the account had at each block number. The function first checks if the block number is greater than the current block number, and if so, it returns 0. It then checks if the block number is lower than the first block number in the checkpoints array, and if so, it returns 0. If the block number is between the first and last block numbers in the checkpoints array, the function uses a binary search algorithm to find the number of votes the account had at the given block number. (autogenerated documentation)
 _delegate(address,address) :
 This function allows a user (the delegator) to delegate their voting power to another user (the delegatee). It does this by setting the delegatee as the new delegate for the delegator in the delegates mapping, and then emitting a DelegateChanged event. It also updates the balances mapping to move the delegator's balance from the current delegate to the new delegate. (autogenerated documentation)
 _transferTokens(address,address,uint96) :
 This function is an internal function that is used to transfer tokens from one address to another. It requires that the source and destination addresses are not the zero address, and then subtracts the amount from the source address and adds it to the destination address. It also emits a Transfer event and calls the _moveDelegates function to update the delegates associated with the source and destination addresses. (autogenerated documentation)
 _moveDelegates(address,address,uint96) :
 This function is used to move delegates from one address to another. It takes three parameters: the source address, the destination address, and the amount of delegates to be moved. It first checks if the source and destination addresses are different and if the amount is greater than 0. If so, it subtracts the amount from the source address and adds it to the destination address. It does this by first retrieving the number of checkpoints for each address and then retrieving the votes from the last checkpoint. It then subtracts the amount from the source address and adds it to the destination address, writing the new values to the respective checkpoints. (autogenerated documentation)
 _writeCheckpoint(address,uint32,uint96,uint96) :
 This function is used to write a checkpoint for a delegatee. It takes in the address of the delegatee, the number of checkpoints, the old votes, and the new votes. It first checks if the number of checkpoints is greater than 0 and if the last checkpoint was from the current block number. If so, it updates the votes for the last checkpoint. Otherwise, it creates a new checkpoint with the current block number and the new votes. Finally, it emits an event to indicate that the delegatee's votes have changed. (autogenerated documentation)
 safe32(string) :
 This function is an internal pure function that takes in a uint and a string as parameters. It checks to make sure that the uint is less than 2^32 and if it is not, it will throw an error message. If the uint is less than 2^32, it will return a uint32 of the input. (autogenerated documentation)
 safe96(string) :
 This function is an internal pure function that takes in a uint and a string as parameters. It checks to make sure that the uint is less than 2^96 and if it is not, it will throw an error message. If the uint is less than 2^96, it will return a uint96. (autogenerated documentation)
 add96(uint96,uint96,string) :
 This function adds two 96-bit unsigned integers (uint96) together and returns the result. It also checks to make sure that the result of the addition is greater than or equal to the first integer (a) to ensure that no overflow occurs. If an overflow does occur, an error message is thrown. (autogenerated documentation)
 sub96(uint96,uint96,string) :
 This function is an internal pure function that subtracts two uint96 values and returns the result. It requires that the second argument (b) is less than or equal to the first argument (a). If this is not the case, an error message is thrown. The function then returns the result of subtracting b from a. (autogenerated documentation)
 getChainId() :
 This function is used to get the chain ID of the current Ethereum network. It does this by using the chainid() assembly instruction, which returns the chain ID of the current network. The function then returns the chain ID as a uint256. (autogenerated documentation)
