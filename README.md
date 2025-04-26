# ecs152a-project-3-p0-solved
**TO GET THIS SOLUTION VISIT:** [ECS152A Project 3 P0 Solved](https://www.ankitcodinghub.com/product/ecs152a-project-3-p0-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;124596&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;ECS152A  Project 3 P0 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
&nbsp;

Reliable and Congestion

Controlled Data Transfer over UDP

The goal of this project is to create a reliable version of UDP which is resistant to network congestion.Assignment Project Exam Help

The project is divided into three different parts to help you slowly build towards the reliable, connection oriented and congestion controlled UDP Berryessa.

Part 1: Adding Connection Support to UDP (UDP Putah) (20 points)

UDP socket can directly start sending data. While UDP’s approach is certainly faster and easier to use, having persistent connections brings with itself benefits like a separate data socket for each connection, allowing servers to parallelize data transfer between multiple simultaneous users, while also ensuring reliability for each data stream.

In this part, you will add connection support to UDP using a three-way handshake (just like TCP!) and create a new version of UDP called UDP Putah.

When a client connects to a server, it will send a handshake message to the server. If the server is willing to connect, it will send the response back to the client telling it that a connection has been established on the server’s end. Finally, the client also sets up a connection and sends an acknowledgement for it back to the server.

Now here comes the tricky part! If you refer back to section 2.7 of the book, TCP has two different types of sockets: a welcoming socket and a connection socket.

The welcoming socket is responsible for listening to incoming connection requests and performing three-way handshakes, while the connection socket is responsible for sharing the actual data. In TCP’s own implementation, the client is abstracted from this whole process. It uses the same port and IP address for both connecting to the server and sharing the data. However, because we are building our reliable transport layer on top of UDP, we do not have the liberty of using the same IP and port for multiple different sockets (refer back to our discussion on multiplexing differences between TCP and UDP, discussed in detail in section 3.2). To overcome this issue, while still maintaining roughly the same process as TCP follows, you will implement the following:

1. A server will listen to the incoming requests using the “accept” function (so far we are following TCP to a tee)

2. A client will connect to a listening server using the “connect” function (so far so good)

3. A three-way handshake will take place between the client and the server (seems familiar)

4. Two new UDP sockets will be created (one on the client and one on the server) and their port numbers will be shared with each other (here we go)

5. All further communication will happen using these two new sockets (which will be running in their separate threads) while the main threads will go back to either accepting or connecting to new clients (we now have two brand new sockets to share data)

Note: Remember that UDP does not have accept and connect functions by default. You will be adding these functions to mimic and implement the functionality described above for UDP Putah.

You are allowed flexibility in your implementation of this detail in your code, however, there are a few constraints to keep in mind:

1. Your code should have separate welcoming sockets and separate connection sockets.

2. You are not allowed to use more than three messages to create a new connection between the client and the server. All the information sharing about the new connection sockets should happen in the same three messages.

3. You should be able to keep running the welcoming socket in a thread to accept new connections while the connection socket should have the capacity to run in a separate thread to transfer data.

4. You are not allowed to add any fields to the custom TCP header that you will design which are not present in the actual TCP header. More discussion about the header is at the end of this part.

Evaluation

For this part, you have to do the following:

1. Run the server using the following command:

python3 server_putah.py –ip XXXX.XXXX.XXXX.XXXX –port

YYYY

Note: As most of you will be running this on a local computer, the IP will be

“localhost” more often than not.

2. The server will start listening for incoming connections. It should now be able to acceptAssignment Project Exam Help

incoming connections

–server_port YYYY

Note: Because we are less concerned about what port the client runs on (as long as it

number.

4. Upon running the command, the client should initiate a three-way handshake with the server. The server will respond back to the handshake and establish a connection. Note: Remember that SYN and SYN/ACK messages do not contain any message body, just the header.

5. Upon the successful establishment of the connection, the client and the server should both print and log the IP address and Port number of the new connection sockets created (remember that the welcoming socket for a server will run on the port that we provide in the command, while the new connection sockets will run on completely different ports).

6. The client would now send data to the server (in this case, a simple “ping” message), while the server would respond with a simple “pong” message to the client. This ping pong should keep on happening indefinitely until we terminate the client using CTRL+C or CMD+C (a keyboard interrupt exception). Upon termination, the client or server being terminated will send a FIN message to the other host and wait for an acknowledgement before closing the connection socket. The other host will send back an acknowledgement and close the connection.

7. Now open another terminal window and run another client using the same command as step 3. Another client should spin up and start playing ping-pong with the server.

8. Log all the interactions and messages between the two clients and the server in the following format:

Source | Destination | Message Type | Message Length

Note: The source and destination here would be the port numbers. The message type tells us which kind of message is being sent. Is it an SYN, SYN/ACK, ACK, DATA, or a FIN message? Here DATA packet is any packet which contains actual data to be transferred and is not one of the other SYN/ACK/FIN packets.

Answer the following questions as part of your report:

1. What are the differences between multiplexing done in a UDP socket vs a TCP socket? What would happen if we were to use the same IP and Port number for transferring data to different clients in our implementation of UDP Putah? (3 points)

2. Why does TCP require three messages to establish the connection? What would go wrong if you were to attempt building the connection with two messages? (3 points)

3. Explain how you implemented the sharing of connection socket port numbers between the client and the server in your implementation. Justify your choice of header and message content in sharing this information. (4 points)

Along with the answers to these questions, submit the python code for the server and client, along with the log files that you generated during your own testing (10 points).

Assignment Project Exam Help

Header for Custom UDP Implementation

Assignment Project Exam Help

points)

different clients, it’s time to add some reliability to it. Remember from our discussions in class that TCP accomplishes reliability using acknowledgements. For each message that the sender sends to the receiver, the receiver must acknowledge it to let the sender know that the message was received successfully. If there’s any packet loss, the acknowledgement will never arrive and the sender will have to resend the packet back to the receiver.

You will implement a similar acknowledgement process as TCP, where instead of acknowledging each individual packet, you will acknowledge the number of bytes that the receiver has successfully received so far. This is known as cumulative acknowledgement. If the receiver has received 1500 bytes so far, it will expect a packet starting with the sequence number 1501. Thus as an acknowledgement for the packet containing a sequence number of 1000, and 500 bytes, the receiver will send an acknowledgement back for 1500 bytes. You will be implementing a variation of the stop-and-wait algorithm for this part (you will be sending only one packet at a time and then waiting for its acknowledgement).

Evaluation

For this part, you have to do the following:

1. Because you are running this on a local server, and the information sharing is happening between two processes running on a local host, there will not be any major bandwidth constraint or packet loss. However, because we want to make things difficult for both you and your implementation of a UDP Solano, you will induce artificial packet loss and delay by doing the following:

a. Your receiver (or what we were calling a server in part 1), will accept two additional arguments, namely, packet loss percentage and round trip jitter. The value of both of the packet loss percentage will be between 0 and 100, while the value of the round trip jitter will be a decimal number between 0 and 1.

b. For each packet received, you will generate a random integer between 0 and 100. If the value of that random integer is equal to or less than the packet loss percentage, you will drop that packet and not send any acknowledgement back to the sender.

c. Before sending each acknowledgement, you will generate a random decimal between 0 and 1. If the value of the random decimal is larger than the round trip jitter, you will sleep the receiver for that value in seconds before sending the acknowledgement back to the sender.

d. Use the default value of packet loss percentage as 10 and round trip jitter of 0.5

2. You will run the receiver using the following command:

python3 receiver_solano.py –ip XXXX.XXXX.XXXX.XXXX

–port YYYY –packet_loss_percentage X

–round_trip_jitter Y –output output.txt

3. You will run the sender (or what you called the client in the previous part) using the following command:

python3 sender_solano.py –dest_ip XXXX.XXXX.XXXX.XXXX

–dest_port YYYY –input input.txt

Note: You can assume for this part that the file will always be a text file, however, you should read and send the file as a regular binary file, which would make it agnostic to the file type used.

4. You will use these two files to test your program:

5. The sender will connect to the receiver using the three-way handshake implemented in part 1. They will also share with each other the sequence numbers they will be using (it’s important to remember here that for both reliability and security concerns, the sequence numbers used by the sender and receiver in TCP do not start from 0, rather they start from a randomly generated 32-bit number, read more about it here: Understanding TCP Sequence and

6. Acknowledgment Numbers – PacketLife.netAfter establishing the connection and opening new sockets for data transfer, the sender willAssignment Project Exam Help).

start sending the file to the receiver. The file will be transferred in packets of size 1000 bytes

will arrive at a different time. Your sender should be able to:

a. Resend correct packets which are lost

and it should not be too short as to introduce a lot more packet loss and timeouts). You can do this by implementing the following timeout interval formula from section

3.5.3:

𝑇𝑖𝑚𝑒𝑜𝑢𝑡Where EstimatedRTT 𝐼𝑛𝑡𝑒𝑟𝑣𝑎𝑙 =is calculated from the weighted 𝐸𝑠𝑡𝑖𝑚𝑎𝑡𝑒𝑑𝑅𝑇𝑇 + 4 * 𝐷𝑒𝑣𝑅𝑇𝑇average of previous RTTs and

is calculated as:

𝐸𝑠𝑡𝑖𝑚𝑎𝑡𝑒𝑑𝑅𝑇𝑇DevRTT represents the variability in the round trip = (1 − 𝛂) * 𝐸𝑠𝑡𝑖𝑚𝑎𝑡𝑒𝑑𝑅𝑇𝑇 time and is calculated as:+ 𝛂 * 𝑆𝑎𝑚𝑝𝑙𝑒𝑅𝑇𝑇

𝐷𝑒𝑣𝑅𝑇𝑇Go through section 3.5.3 carefully to learn more about default values suggested for = (1 − β) * 𝐷𝑒𝑣𝑅𝑇𝑇 + β * |𝑆𝑎𝑚𝑝𝑙𝑒𝑅𝑇𝑇 − 𝐸𝑠𝑡𝑖𝑚𝑎𝑡𝑒𝑑𝑅𝑇𝑇|

each of these variables and when to update the timeout interval.

7. You will calculate the following statistics for the file transfer and output them at the sender’s terminal:

a. Time taken to transfer each file

b. Total bandwidth achieved (amount of data sent/total time taken) for each file

c. Packet loss observed (Packets lost/Packets Sent) for each file

8. You will also log all the interactions and messages between the two clients and the server in the following format:

Source | Destination | Message Type | Message Length

Note: The source and destination here would be the port numbers. The message type tells us which kind of message is being sent. Is it an SYN, SYN/ACK, ACK, DATA, or a FIN message? Here DATA packet is any packet which contains actual data to be transferred and is not one of the other SYN/ACK/FIN packets.

9. Because our UDP Solano can accept multiple clients; run the same command as step 3 on a different terminal to simultaneously start another file transfer. The receiver should be able to handle both file transfers at the same time.

10. You will repeat this process once for the smaller file, and then again for the larger file.

Answer the following question as part of your report:

1. Explain your implementation of sequence and acknowledge numbers. Why do both sender and receiver maintain separate sequence and acknowledgement numbers? (3 points)

2. Explain and justify the additional header fields you needed to add compared to part 1 for this implementation. (3 points)

3. How would the performance of this file transfer have been affected if we did not use separateAssignment Project Exam Help

welcoming and connection sockets? (4 points)

Along with your report, submit the python code for both the sender and receiver, along with the log

(60 points)

For this last part, we will be adding a flavour of congestion control to UDP Solano (making it a connection-oriented, reliable, congestion-controlled UDP Berryessa, quite a mouthful).

Remember from our lectures and discussions (along with your reading of sections 3.6 and 3.7), congestion control is another salient feature of TCP. In the previous part, we were sending only one packet at a time and then waited for its acknowledgement. But in this part, we will dynamically increase the number of packets that we are sending and adjust the different parameters based on how TCP Tahoe and TCP Reno implement congestion control.

Evaluation

For this part, you have to do the following:

1. Introduce another terminal argument to the receiver: bdp (bandwidth-delay product). This argument represents the maximum amount of data that can be sent on the network at a single time. The receiver should be aware of the rate at which the sender is sending data. If the rate at which the sender is sending data (number of packets sent in one window) exceeds the bdp, the receiver would enter into a congestion state. In a congestion state, you will multiply the packet loss percentage by three and triple the amount of time that the receiver sleeps when the round-trip jitter condition is triggered. Use the default value of bdp as 20,000. (Hint: remember that the congestion window is implemented on the sender’s side, not the receiver’s side. To send that congestion window size to the receiver, you can repurpose the receive window field in the TCP header specification.)

2. You will use the following command to run the receiver.

python3 receiver_berryessa.py –ip XXXX.XXXX.XXXX.XXXX

–port YYYY –packet_loss_percentage X

–round_trip_jitter Y –bdp Z –output output.txt

3. On the sender’s side, you will implement both TCP Tahoe and Reno (You can read more about it in section 3.7 and by following this link: TCP Tahoe and TCP Reno GeeksforGeeks). We should be able to switch the TCP implementation using a terminal switch tcp_version.

4. You will reuse the logic implemented in the previous part for setting a variable timeout interval based on network conditions.

5. You will use the following command to run the sender:

python3 sender_berryessa.py –dest_ip XXXX.XXXX.XXXX.XXXX –dest_port YYYY –tcp_version tahoe/reno –input input.txt

6. You will log the following information for each message sent:

Source | Destination | Message Type | Message Length | State | CWND

Note:Assignment Project Exam HelpHere the state will tell the overall congestion control state the network is following. It

can vary between congestion avoidance and slow start. The CWND will inform you about the window size currently being used by the sender.

the TCP version for this client. The receiver should be able to connect to both clients at the same time and successfully complete the transfer of files.

9. Similar to the previous part, you will repeat this process once for the smaller file, and once for the larger file.

For this part you will calculate the following statistics at the sender’s end:

1. Time taken to transfer each file

2. Total bandwidth achieved (amount of data sent/total time taken) for each file

3. Packet loss observed (Packets lost/Packets Sent) for each file

In addition to these statistics, you will also monitor the change in congestion window size after each transmission round (when all packets in a CWND have been sent and acknowledged) to plot graphs similar to the following for both Tahoe and Reno implementations (10 points):

Answer the following questions as part of your report: Assignment Project Exam Help

1. Explain and justify the additions to your packet header to implement this part as compared to part 2. (3 points)

(from a slow start to congestion avoidance and vice versa), explain the reason behind the change, and report the values of CWND and Slow Start Threshold (SSThreshold) before and after the state change. (12 points)

Compare it with the bandwidth that you measured in part 2. Do you notice any significant difference between these implementations? Explain why there is or why there is not a difference. (10 points)

4. Based on your experience and results in designing these different models, what else can be done to improve the bandwidth usage of your network? (5 points)

Along with the report, submit the python code for the receiver and sender along with the log files generated (20 points).

Testing Environment:

All submissions will be tested on Python 3+.

—————————————— Best of luck —————————————

Submission Page

Team Member 1:

Team Member 2: Assignment Project Exam Help

______________________________ ________________________ ________________
