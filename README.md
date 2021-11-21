# PR_LAB2

This repository holds the second laboratory work for the subject "Programarea în rețea" - from UTM, FAF.

It contains the following files:
* main.py - the implimentation of the main flask module.
* db_manager.py - the file implementing the Data Base Manager.
* tcp_server.py - the file implementing the TCP server.
* udp_server.py - the file implementing the UDP serber.
* database.db - the sqlite3 database file.

This laboratory work is implimenting the following communication protocols:
* HTTP - the flask application is taking HTTP requests and creates other reuquests.
* TCP - created by the flask application for the TCP server to add remainders.
* UDP - created by the flask application for the UDP server to add tasks.
* STMP and SSL - created by the flask application for the gmail server for sending emails.

To run them application you should run the following commands in different terminals:
1. ```python main.py```
2. ```python tcp_server.py```
3. ```python udp_server.py```

After that you can send requests to the following endpoint: ```http://127.0.0.1:5000/```

The structure of the json for sending emails is the following:
```json
{
    "type" : "send-email",
    "body" : {
        "receiver-email" : "vpapaluta@gmail.com",
        "email-message" : '''Hello world!'''
    }
}
```

The structure of the json for adding remainders is the following:
```json
{
    "type" : "add-remainder",
    "body" : {
        "remainder-name" : "rem-name1",
        "remainder-body" : '''Hello world!''',
        "remainder-time" : "7 Feb 2022, 10:00:00"
    }
}
```

The structure of the json for adding tasks is the following:
```json
{
    "type" : "add-task",
    "body" : {
        "task-name" : "task-name1",
        "task-body" : '''You must do this and this...''',
        "task-due-date" : "7 Feb 2022, 10:00:00"
    }
}
```
