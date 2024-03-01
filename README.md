# friend_requests
Write a SQL query that returns the three users who have sent the most friend requests. Your query should return the username and number of requests sent. 

Select user_name
From (select requester_id, count(*) as request_count from friend_requests
Group by requester_id
Order by request_count desc 
Limit 3)t, users
Where t.requester_id = users.user_id;
