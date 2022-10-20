    1. High level approach
Approaching this project the first thing that we realized is that we were going to be receiving messages with multiple 
different types. To process each message and perform the correct task we created a "processMsg" method that would take 
in the message, extract its dictionary from the string we received, check its type, and then perform a function
depending on what type of message it is. For each different type we created a different function that only gets called 
when we receive a message of the corresponding type. We also noticed that for some tasks we needed to check whether we 
should be forwarding a message or not depending on whether we were sending a peer/providers message or a customer to a 
peer/provider or a customer. since we were doing it many times we decided to abstract this check into its own function.
With these abstractions, our code became alot more readable and less complex. Once we broke down our project into these
parts it was just a matter of tackling each task a method at a time.
    
    2. Challenges
Being the first time really working with ips, really understanding the semantic of the peers attributes was a challenge
 a really important step to completing the project. One of the biggest challenges related to this was figuring out the 
best way to compare these attributes while also keeping our code efficient and readable. Another challenge was
