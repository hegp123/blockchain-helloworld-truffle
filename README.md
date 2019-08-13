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
    $ web3.eth.getTransaction('0x1ac045fbe9e53c5ae82fd60649e9c3c9ddd24d243eb1ba125f87a8c4b8251ae5');  //obtiene informacion de alguna transaccion
    $ web3.eth.getTransactionReceipt('0x1ac045fbe9e53c5ae82fd60649e9c3c9ddd24d243eb1ba125f87a8c4b8251ae5');  //devuelve el recibo de la transaccion
        si status:  0x1 , la transaccion fue exitosa
        si status:  0x0 , la transaccion fue fallida, occurio al gun error
    $ Migrations.deployed().then(c => instance = c);  // interactuar con smart contracts
    
    --ejemplo puntual en el ejercicio de usuario
    $ UsersContract.deployed().then(c => instance = c);  // interactuar con smart contracts
    $ instance.join("Capitan", "América", {from: web3.eth.accounts[0], gas: 1200000});
