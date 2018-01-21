Execute code via CLI
```
$ geth --exec "eth.accounts" attach
$ geth --exec "eth.syncing" attach
$ geth --exec "eth.blockNumber" attach
$ geth --exec 'loadScript("/tmp/checkbalances.js")' attach
$ geth --jspath "/tmp" --exec 'loadScript("checkbalances.js")' attach
```

[Transfer](https://ethereum.gitbooks.io/frontier-guide/content/ether_transfer.html)
```
eth.sendTransaction({
  from: '0x036a03fc47084741f83938296a1c8ef67f6e34fa',
  to: '0xa8ade7feab1ece71446bed25fa0cf6745c19c3d5',
  value: web3.toWei(1, "ether"),
})
```

[Account management](https://github.com/ethereum/go-ethereum/wiki/Managing-your-accounts)
```
function checkAllBalances() {
  var totalBal = 0;
  for (var acctNum in eth.accounts) {
    var acct = eth.accounts[acctNum];
    var acctBal = web3.fromWei(eth.getBalance(acct), "ether");
    totalBal += parseFloat(acctBal);
    console.log("  eth.accounts[" + acctNum + "]: \t" + acct + " \tbalance: " + acctBal + " ether");
  }
  console.log("  Total balance: " + totalBal + " ether");
};
```

```
> checkAllBalances();
```

```
$ irb
> require "json"
> accounts = JSON.parse(%x[geth --exec "eth.accounts" attach])
> => ["0x5177535e39fe5d0ced2e34bbd5a5cb8c537e4d1b"]
```
