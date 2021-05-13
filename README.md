# TransactionApplication
A web service for processing payments.

POST endpoint /payments will create a payment resource, which accepts 2 mandatory fields (amount, debtorIban).
For each transaction, an UUID and a timestamp will be generated.

POST endpoint /payment-files accepts .csv files, which have 2 columns (amount, debtorIban) and process these payments also.
The imported payments from the .csv file will also get genereated UUID and timestamps. 

Both POST endpoints have a set of rules. The amount must be larger than 0 and the debtorIban has to be an IBAN from a Baltic country
(Estonia, Latvia, Lithuania).

GET endpoint /payments returns a list of all payments. The returned payments have an id(UUID), the amount, the debtor IBAN and createdAt timestamp. The /payments endpoint can be filtered with an optional debtorIban query "GET /payments <debtorIban>".
  
