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
best way to compare these attributes while also keeping our code efficient and readable. Another challenge was figuring 
how to format the messages we were sending, who to send them to, and reading through the filled up terminal to see 
where we went wrong. Lastly, the biggest obstacle was aggregation. Figuring out how to find numerically adjacent ips 
and how to aggregate the two entries in our table once we find them was very tough. Once we did find them, edited the 
network, edited the netmask, and finalized the table, we realized that how we were doing it was creating gaps between 
potentially aggregatable entries which we didn't know how to fix. After a lot of searching and analyzing how 
aggregation works we figured out that by using the netmask we could bridge these gaps.

    3. Properties/Features
- Abstracting the functions performed for each type of message.
- Creating a method to process received messages and send the information to the corresponding method.
- A uniform comparison chain to compare attributes to minimize errors.
- Use of netmask differences to find the reach of routing table entries for aggregation. 
- Storing deep copies of update messages in our routing table to eliminate the chance of mistakenly editing our table.
- Checking for peer/provider connections only before sending the message, so we didn't have to check our entire table 
  for these matches.

        4. Testing
We tested our code by running the test cases provided by the professor. We also tested our code using print statements 
to make sure that we were receiving the correct messages and that we were sending the correct messages. We also used 
print statements to verify the contents of our forwarding table. We would also run our code through the terminal and use
the outputted messages to verify that our code was working correctly, and to debug any issues we were having. For example, 
we had an issue where we would make a shallow copy of our forwarding table and when we would try to modify the copy it
would also modify the original. We fixed this by making a deep copy of the forwarding table. The copy issue was found 
by running our code through the terminal and using print statements to check the contents of our forwarding table.


