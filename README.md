# JAGUAR BANK NETWORK

> This is the "JAGUAR BANK" of Hyperledger Composer samples, which demonstrates the core functionality of Hyperledger Composer by changing the value of an asset.

This business network defines:

**Participant**
`Customer`
`Manager`

**Asset**
`Account`

**Transaction**
`accountTransfer`


Account are owned by a Customer, and the value property on a Account can be modified by submitting a accountTransfer.

To test this JAGUAR BANK NETWORK in the **Test** tab:

Create a `Customer` participant:

```
{
  "$class": "org.example.basic.Customer",
  "customerId": "0456",
  "firstName": "",
  "lastName": "",
  "cellphone": "",
  "email": ""
}
```

Create a `Manager` participant:

```
{
  "$class": "org.example.basic.Manager",
  "managerId": "8755",
  "firstName": "",
  "lastName": "",
  "cellphone": "",
  "email": ""
}
```

Create a `Account` asset:

```
{
  "$class": "org.example.basic.Account",
  "accountd": "7633",
  "balance": 0,
  "customer": "resource:org.example.basic.Customer#2041",
  "manager": "resource:org.example.basic.Manager#9857"
}
```

Submit a `AccountTransfer` transaction:

```
{
  "$class": "org.example.basic.AccountTransfer",
  "amount": 2000,
  "accountFrom": "resource:org.example.basic.Account#8500",
  "accountTo": "resource:org.example.basic.Account#7539"
}
```

After submitting this transaction, you should now see the transaction in the Transaction Registry and that a `SampleEvent` has been emitted. As a result, the value of the `amount` should now be `new value` in the Asset Registry.

Congratulations!

## License <a name="license"></a>
Hyperledger Project source code files are made available under the Apache License, Version 2.0 (Apache-2.0), located in the LICENSE file. Hyperledger Project documentation files are made available under the Creative Commons Attribution 4.0 International License (CC-BY-4.0), available at http://creativecommons.org/licenses/by/4.0/.
