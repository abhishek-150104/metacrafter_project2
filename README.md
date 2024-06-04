# metacrafter_project2
Project: Create a Token
Here we created a contract called MyToken that will mint tokens and add it to given addresses.
We have declared few public variable:
 string public token = "REALITY";  //Token name
 string public symbol = "RLY";   // Token abbrevation
 uint public total_supply = 0;  // total supply of token
And another mapping variable that associates the address with the balances
 mapping (address => uint) public balances;
We have few function Mint for minting the token which takes address and balance as parameter
  function mint(address _address, uint _balance) public {
      balances[_address] += _balance;
      total_supply += _balance;

    }
  another function called burn which burn the token takes two arguement address and balance
   function burn(address _address, uint _balance) public {
      if(balances[_address] >= _balance) {
         balances[_address] -= _balance;
         total_supply -= _balance;
      }
    }
    In above we have a conditional to check wheather the token to be burned ids less than theeoken present in that address
