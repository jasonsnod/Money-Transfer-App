# Money-Transfer-App
Server-side code for a money transfer app.

# Goal of project

This project was a class project to mimic the back-end infrastructure of a payment transfer application. It utilizes PostgreSQl, Java, and Spring Boot as back-end technologies. The goal was to implement an MVC design structure, implement a DAO pattern, database design, and data design for communication between the client and server.

## Business specifications

1. Users need to be able to register with a username and password.
   1. A new registered user starts with an initial balance of $1,000.
2. Users need to be able to log in using registered username and password.
   1. Logging in returns an Authentication Token. This token is included with all subsequent interactions with the system that are not registering and logging in.
3. Logged in users need to be able to see their Account Balance.
4. Logged in users need to be able to *send* a transfer of a specific amount of money to another registered user.
   1. users choose from a list of users to whom they send money.
   2. Users cannot send money to themselves.
   3. A transfer includes the User IDs of the from and to users and the amount of money.
   4. The receiver's account balance is increased by the amount of the transfer.
   5. The sender's account balance is decreased by the amount of the transfer.
   6. Users cannot send more money than they have in their account.
   7. Users can't send a zero or negative amount.
   8. A Sending Transfer has an initial status of *Approved*.
5. Logged in users need to be able to see transfers they have sent or received.
6. Logged in users need to be able to retrieve the details of any transfer in their transfer history based upon the transfer ID.
7. Logged in users need to be able to *request* a transfer of a specific amount of money from another registered user.
   1. Users should be able to choose from a list of users to request money from.
   2. Users cannot request money from themselves.
   3. Users can't request a zero or negative amount.
   4. A transfer includes the User IDs of the from and to users and the amount of money.
   5. A Request Transfer has an initial status of *Pending*.
   6. No account balance changes until the request is approved.
   7. The transfer request should appear in both users' list of transfers (refer to #5).
8. Logged in users need to be able to see their *Pending* transfers.
9. Logged in users need to be able to either approve or reject a Request Transfer.
   1. Users can't "approve" a given Request Transfer for more money than they have in their account.
   2. The Request Transfer status is *Approved* if sending user approves, or *Rejected* if sneding user rejects the request.
   3. If the transfer is approved, the requester's account balance is increased by the amount of the request.
   4. If the transfer is approved, the requestee's account balance is decreased by the amount of the request.
   5. If the transfer is rejected, no account balance changes.

## Examples of what user would see as they interact with application.

### Use case 3: View current balance
```
Your current account balance is: $9999.99
```

### Use case 4: Send money
```
-------------------------------------------
Users
ID          Name
-------------------------------------------
313         Bernice
54          Larry
---------

Enter ID of user you are sending to (0 to cancel):
Enter amount:
```

### Use case 5: View transfers
```
-------------------------------------------
Transfers
ID          From/To                 Amount
-------------------------------------------
23          From: Bernice          $ 903.14
79          To:    Larry           $  12.55
---------
Please enter transfer ID to view details (0 to cancel): "
```

### Use case 6: View specific transfer details
```
--------------------------------------------
Transfer Details
--------------------------------------------
 Id: 23
 From: Bernice
 To: Me Myselfandi
 Type: Send
 Status: Approved
 Amount: $903.14
```

### Use case 7: Requesting money
```
-------------------------------------------
Users
ID          Name
-------------------------------------------
313         Bernice
54          Larry
---------

Enter ID of user you are requesting from (0 to cancel):
Enter amount:
```

### Use case 8: View all ending requests
```
-------------------------------------------
Pending Transfers
ID          To                     Amount
-------------------------------------------
88          Bernice                $ 142.56
147         Larry                  $  10.17
---------
Please enter transfer ID to approve/reject (0 to cancel): "
```

### Use case 9: Approve or reject pending transfer
```
1: Approve
2: Reject
0: Don't approve or reject
---------
Please choose an option:
```

## **To review code for project, please contact Jason Snoddy** 
```
Contact info: https://www.linkedin.com/in/jsno/
```
