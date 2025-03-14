# MIST 4610-Project1-Group1

The event manager can use an event management system to ensure smooth operations. Our Event Management Database is designed to Improve efficiency.Administrative tasks such as ticket sales, bookings, booking location, etc., are automated, making event planning more streamlined. Ourdatabse will also aid in Better decision making  Allows managers to obtain insight regarding vendor availability, attendee demographics, etc. which can help managers adjust marketing when needed. Additionally managers can easily track revenue coming in from attendees, generate reports for top-spending attendees, etc. Lastly multi-user access can allow multiple vendors, organizers, ticketing partners, etc. to access the database while maintaining data integrity.


##  Database
The event management database model depicted in the image is designed to efficiently track and manage various aspects of event planning. The Clients table stores client details, linking them to the Events table, which contains event-specific information such as event names and dates. Events are associated with Bookings, which connect clients to Venues, storing details like venue capacity and location. The Attendees table records participant details, including demographics and referral sources, and links them to their respective events. Financial transactions are managed through Client_Payments, which track payments made by clients for bookings, and Attendee_Payments, which record attendee payment details for event participation. The database's structured relationships ensure seamless coordination between clients, events, venues, and financial transactions, enhancing operational efficiency and data accuracy for event managers.
<img width="900" alt="database for GP" src="https://github.com/user-attachments/assets/1ec88dd0-dd44-47cd-811a-c478e2787e26" />


## Data Dictionary 
<img width="900" alt="Screenshot 2025-03-13 at 7 03 38 PM" src="https://github.com/user-attachments/assets/f82b8671-0549-43bf-a2a4-fbc398e860c9" />

<img width="900" alt="Screenshot 2025-03-13 at 7 11 43 PM" src="https://github.com/user-attachments/assets/a30bc4a7-3f48-475c-b781-cbbfbcbe842b" />
<img width="900" alt="Screenshot 2025-03-13 at 7 22 43 PM" src="https://github.com/user-attachments/assets/e040b47c-a457-4e10-aa0a-e1626e190fa8" />
<img width="900" alt="Screenshot 2025-03-13 at 7 26 50 PM" src="https://github.com/user-attachments/assets/a730aa21-63de-4f42-a97b-7f000a89f7ef" />
<img width="900" alt="Screenshot 2025-03-13 at 9 26 40 PM" src="https://github.com/user-attachments/assets/b495a974-2db7-4d34-9683-772c50ab28d3" />
<img width="900" alt="Screenshot 2025-03-13 at 9 32 30 PM" src="https://github.com/user-attachments/assets/d62af6d9-0a2e-4b0b-b247-d0fe197d7f30" />
<img width="900" alt="Screenshot 2025-03-13 at 9 36 13 PM" src="https://github.com/user-attachments/assets/a62f205d-ecdd-4f3c-93b6-7dc20fcdca98" />



## Queries 
1. Querey 1 provides key insights into client booking behavior and total payments, helping businesses identify their most valuable and engaged customers. By retrieving a list of clients who have made multiple bookings, it highlights repeat customers who are driving sustained revenue. The query counts the total number of bookings per client and sums up their total payments, offering a clear picture of customer spending patterns.

Filtering out clients with only one booking ensures that the analysis focuses on high-value customers, which is useful for customer retention strategies. Ordering the results by total bookings and then by total payments allows businesses to prioritize their top clients for loyalty programs, exclusive discounts, or premium services. This insight can be leveraged for targeted marketing efforts, optimizing customer relationship management, and improving service offerings to encourage continued engagement. 

This query works by Retrieving a list of clients who have made multiple bookings.
   Counting the total number of bookings per client (COUNT(Bookings.booking_id)).
   Sums up the total payment made by each client (SUM(Client_Payments.client_payment_amount)).
 Uses HAVING COUNT(Bookings.booking_id) > 1 to filter only those who booked more than once.
 Orders the results first by total bookings (descending) and then by total payments (descending)
<img width="463" alt="image (3)" src="https://github.com/user-attachments/assets/98871ba1-64fb-494d-89ab-01991f78307f" />
<img width="342" alt="image (4)" src="https://github.com/user-attachments/assets/a5a8f926-1211-418c-9c86-bf763557123f" />

2. Query 2 Sums up the client payments and attendee payments for each event.
Adds both revenues to get total revenue.Groups by client ID and event name to get revenue per-client for each event.Orders by total revenue in descending order to show the highest earning events first. This allows us to dentify high-value clients who contribute the most revenue and Compare revenue across different events to identify successful vs. underperforming ones.


<img width="616" alt="image (5)" src="https://github.com/user-attachments/assets/ca84e1e1-9759-4df9-a544-271666021d3e" />

<img width="554" alt="image (6)" src="https://github.com/user-attachments/assets/fb6d6d6b-4c34-42cd-8d4a-0036d5b09917" />



3. Query 3 returns the top 5 highest-grossing events. This query works by Calculating total revenue for each event.
Sums client payments (SUM(Client_Payments.client_payment_amount)).
Sums attendee payments (SUM(Attendee_Payments.att_payment_amount)).
Computes overall revenue per event.
Orders by total revenue in descending order.
Uses LIMIT 5 to fetch only the top 5 highest-grossing events.

<img width="608" alt="image (8)" src="https://github.com/user-attachments/assets/9153b98f-acf3-4fbb-94f0-de3417837658" />

<img width="442" alt="image (9)" src="https://github.com/user-attachments/assets/c2a35988-7be1-4843-9010-20f402e5f209" />


4.Query 4 gives the user insight into the events with the most attendees. This query helps to provide insights like determining which types of events perform best, enabling targeted marketing strategies to maximize attendance. Additionally it can guide decisions on venue selection,staffing,and resource allocation based on historical attendance data. Moreover managers will be provided with data on which events attract the most people, allowing them to analyze trends and replicate successful strategies.Finally this query ensures that event spaces are adequately sized and staffed to handle expected crowds, reducing overcrowding and improving the attendee experience. This querey works by: Displaying the event ID, event name, and count of total attendees per event. 
Joining attendees table with event table so we can acquire the count of total attendees.
Groups by event ID and event name to show per-event statistics.
Orders by total attendees in descending order to highlight the most attended events first.

<img width="526" alt="image (10)" src="https://github.com/user-attachments/assets/f675843f-1537-46ce-bb7c-2658210ce994" />
<img width="257" alt="image (12)" src="https://github.com/user-attachments/assets/fc454169-b22a-4456-b25f-676446340aba" />
<img width="255" alt="image (13)" src="https://github.com/user-attachments/assets/d08183d2-2254-4ca6-bad7-abb5349ac9e3" />


5.Query 5 returns the total number of events hosted by each client.providing valuable insights into client engagement and event-hosting activity. By counting the total number of events booked by each client, businesses can identify their most active and loyal customers. This data helps event management companies or venues recognize high-value clients who may be eligible for loyalty programs, special discounts, or personalized services.

Additionally, ranking clients by the number of events hosted enables companies to allocate resources efficiently, ensuring that frequent clients receive priority support and engagement. The insights derived from this query also aid in strategic marketing efforts by targeting less active clients with promotions or incentives to increase their event bookings. Furthermore, it provides a clear snapshot of customer distribution, helping management analyze patterns in event hosting and develop data-driven strategies to enhance client retention and satisfaction.

This query works by Counting the total number of events booked by each client.
Grouping results by client ID, first name, and last name.
Ordering by total events hosted in descending order to show most active clients first.
<img width="460" alt="image (14)" src="https://github.com/user-attachments/assets/cf38eafc-a914-4309-9078-402b0c17932d" />

<img width="263" alt="image (15)" src="https://github.com/user-attachments/assets/98ef7077-a1f1-484d-8735-1f1a238bd68f" />

6. Query 6 



## Database Information
