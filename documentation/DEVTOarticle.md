# Distributed Ledger and ethereum token creation

Basically, **distributed ledger** is the concept of sharing data evolution control in a common network. One of the most famous examples of this are BITCOINS, which works over a blockchain, a data base distributed between several participants (nodes) inside a ledger, which contains the updated status of each transaction between the nodes. These nodes are connected using a specific protocol.

The key of this system's movement lays on Token, elements that contains information and are encrypted. This token could act as a currency, vote, message, or anything that can be fixed in Distributed Ledger system. Several startups saw in this model new opportunities and efficient ways to approach to a better security and lower cost solutions. This way, DL is not always pictured in currency terms, but also thought to be an interesting option in energy industry ([Powerledger](https://tge.powerledger.io)), IoT ([Filament](https://filament.com)), communication or Voting systems ([Horizon State](https://horizonstate.com)).

Ethereum (an uprising cryptocurrency) has a wallet application that let developers freely deploy c++ contracts for token creation or nodes organizations in a virtual sandbox or in the real world. This is a lot of fun and makes the understanding of distributed ledger clearer for developers. The original documentation can be found [here](https://www.ethereum.org/dao) and [here](https://www.ethereum.org/token), and I will sum up how to create a token contract. Also, there's a wider explanation about DL in spanish and some contract examples in my [github repository](https://github.com/terceranexus6/ethereum_lab), please feel free to take a look at it and suggest any issues or PR. The project development is also pictured in a kanban styled board in the repo.

Okay so the basic token contract handles the initial supply of tokens that the owner (the contract developer) has, and the basic transfer funtion that includes checkings and token ownership changing.

```
contract MyToken {
    /* This creates an array with all balances */
    mapping (address => uint256) public balanceOf;

    /* Initializes contract with initial supply tokens to the creator of the contract */
    function MyToken(
        uint256 initialSupply
        ) {
        balanceOf[msg.sender] = initialSupply;              // Give the creator all initial tokens
    }

    /* Send coins */
    function transfer(address _to, uint256 _value) {
        require(balanceOf[msg.sender] >= _value);           // Check if the sender has enough
        require(balanceOf[_to] + _value >= balanceOf[_to]); // Check for overflows
        balanceOf[msg.sender] -= _value;                    // Subtract from the sender
        balanceOf[_to] += _value;                           // Add the same to the recipient
    }
}
```

But for creating a more complex cryptocurrency (that can be also used for other purposes such as voting, as mentioned) we should settle down some more details. For example, we should define the basic variables for the token identification:

```
// Public variables of the token
string public name;
string public symbol;
uint8 public decimals = 18;
// 18 decimals is the strongly suggested default, avoid changing it
```
And a more conplex transfer function which takes cares of saving balances for the future.

```
function _transfer(address _from, address _to, uint _value) internal {
    // Prevent transfer to 0x0 address. Use burn() instead
    require(_to != 0x0);
    // Check if the sender has enough
    require(balanceOf[_from] >= _value);
    // Check for overflows
    require(balanceOf[_to] + _value > balanceOf[_to]);
    // Save this for an assertion in the future
    uint previousBalances = balanceOf[_from] + balanceOf[_to];
    // Subtract from the sender
    balanceOf[_from] -= _value;
    // Add the same to the recipient
    balanceOf[_to] += _value;
    Transfer(_from, _to, _value);
    // Asserts are used to use static analysis to find bugs in your code. They should never fail
    assert(balanceOf[_from] + balanceOf[_to] == previousBalances);
}
```
