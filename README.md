# TaskManager

Require npm packages:
express, body-parser, cors, nodemon

Supported functionalities
1) Add a new task.
2) View all the tasks.
3) View a particular task.
4) Update a particular task.
5) Remove a particulate task.
6) View tasks based on the priority level.
7) Filter task based on the completion status.
8) Sort the tasks in ascending or decending order by the creation time.

curl commands

1) To add a new task - 
curl -X POST -d '{"id": "17", "title": "Wakeup early", "description": "Should wake up early", "completionStatus": false, "priorityLevel": "High"}' -H 'Content-Type: application/json' 'http://localhost:3003/tasks'

2) To view all the tasks - 
curl 'http://localhost:3003/tasks'

3) To view a particular task. we should pass the id of the task in the url. ex 17 - 
curl 'http://localhost:3003/tasks/17'

4) To update a particulare task - 
curl -X PUT -d '{"completionStatus": true, "priorityLevel": "low"}' -H 'Content-Type: application/json' 'http://localhost:3003/tasks/17'

5) To remove a particular task - 
curl -X DELETE 'http://localhost:3003/tasks/17'

6) To filter task based on the priority. Priority level can be low, medium, and high - 
curl 'http://localhost:3003/tasks/priority/low'

7) To sort a task by the creation time. asc for ascending and desc for descending - 
curl 'http://localhost:3003/tasks/?sort=olderFirst'
curl 'http://localhost:3003/tasks/?sort=latestFirst'
