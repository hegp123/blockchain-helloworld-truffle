TRUFFLE
1. crear carpeta para el desarrollo
2. ubicarse en la carpeta desde una consola
3. ejecutar:  $ truffle init


## COMPILAR: genera carpeta build
$ truffle compile


## DEPLOY:  este tambien compila los smarts contracts
$ truffle deploy --network development

#SABER QUE TENEMOS DESPLAGADO EN CADA RED
$ truffle networks

## RESET:  fuerza a truffle a olvidar las dirreciones donde esta desplegado los smart contrats, y vuelve a desplegarlos
## esto es muy util en desarrollo
$ truffle deploy --reset --network development

## CONSOLA DE TRUFFLE
## aca podemos utilizar la libreria web3  y todos sus comandos
$ truffle console --network development
    **##** comandos de web3
    $ web3.version
    $ web3.eth.getAccounts((error, acc)=> {accounts = acc });   // busca las cuentas
    $ web3.eth.getBalance(accounts[0]);  //cantidad de ether que tiene la cuenta 0   formato bitnumber
    $ web3.eth.getBalance(accounts[0]).toNumber();  //cantidad de ether que tiene la cuenta 0  formato Wei
    $ web3.toWei(35, 'ether');  // convertir desde ether
    $ web3.fromWei(web3.eth.getBalance(accounts[0]).toNumber(), 'ether');  //convertir en Ether
    $ web3.eth.sendTransaction({from: accounts[3], to: accounts[0], value: web3.toWei(15, 'ether') });  // enviar divisas de una cuenta a otra
