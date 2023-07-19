## My Aproach 
![Alt text](image-1.png)

# Merkle Tree Gift List  

Your project this week is to build an application which gives out gifts, but only to names on the list. The catch is that on the server you are only allowed to store one 32 byte value in the server memory. This 32 byte value has to be enough for the server to be able to determine who is on the list.

### Hints

Think of the client as the prover here. They are the ones trying to prove to the server that the one name is in the list. Likewise think of the server as the verifier here. They are taking the client's proof and, using minimal information, able to verify that the name sent from the client is actually in the list.

To get started with the repository, clone it and then run `npm install` in the top-level directory to install the depedencies.

There are three folders in this repository:

## Client

You can run the client from the top-level directory with `node client/index`. This file is a script which will send an HTTP request to the server.

Think of the client as the _prover_ here. It needs to prove to the server that some `name` is in the `MERKLE_ROOT` on the server. 

## Server

You can run the server from the top-level directory with `node server/index`. This file is an express server which will be hosted on port 1225 and respond to the client's request.

Think of the server as the _verifier_ here. It needs to verify that the `name` passed by the client is in the `MERKLE_ROOT`. If it is, then we can send the gift! 

## Utils

There are a few files in utils:

- The `niceList.json` which contains all the names of the people who deserve a gift this year (this is randomly generated, feel free to add yourself and others to this list!)
- The `example.js` script shows how we can generate a root, generate a proof and verify that some value is in the root using the proof. Try it out from the top-level folder with `node/example.js`
- The `MerkleTree.js` should look familiar from the Merkle Tree module! This one has been modified so you should not have to deal with any crypto type conversion. You can import this in your client/server
- The `verifyProof.js` should also look familiar. This was the last stage in the module. You can use this function to prove a name is in the merkle root, as show in the example.


## Result:
![Alt text](image.png)