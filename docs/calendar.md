# JOT Calendar
This page outlines the modeling of calendar objects and how they are accessed with the JOT API.

## Overview
A calendar is used to group related components and define additional attributes and behaviours of such a group. For example, a calendar may define a roster for a team, or a task list for a project, or maybe a schedule of events for an automated system.

### Calendar API
Whilst a JOT Calendar follows the iCalendar specification for Calendar properties, it does not follow the same nesting of components within a Calendar resource. Rather, the calendar and it's components are defined as different resource types accessible via different endpoints. So for a JOT calendar, the JSON structure is defined as follows:

        {
            "uid":"1",
            "name":"JustIn",
            "description":"",
            "source":"https://www.abc.net.au/news/feed/51120/rss.xml",
            "url":"https://www.abc.net.au/news/justin/",
            "image":"https://www.abc.net.au/news/image/8413416-1x1-144x144.png",
            "last-modified":"20210304T055223Z"
        }
    
The available endpoints for calendar management are defined in the following table.

| Endpoint         | Action            | Description                                          | REST Verb |
|------------------|-------------------|------------------------------------------------------|-----------|
| `/calendars`     | `list-calendars`  | Returns a filtered list of existing calendar objects | `GET`     |
| `/calendars`     | `create-calendar` | Create and return a new calendar object              | `POST`    |
| `/calendar{Uid}` | `get-calendar`    | Returns a single existing calendar object            | `GET`     |
| `/calendar{Uid}` | `set-calendar`    | Replace an existing calendar object                  | `PUT`     |
| `/calendar{Uid}` | `update-calendar` | Update an existing calendar object                   | `PATCH`   |
| `/calendar{Uid}` | `delete-calendar` | Delete an existing calendar object                   | `DELETE`  |

### Calendar Persistence
The Calendar `UID` property is a feature of the primary key for persistence, however it may also incorporate other elements to support multi-tenancy, etc. For example, with DynamoDB a calendar record is as follows:

| PK                     | SK                     | UID | TYPE     | DATA | Owner | Group |
|------------------------|------------------------|-----|----------|------|-------|-------|
| `GROUP`#CALENDAR#`UID` | `GROUP`#CALENDAR#`UID` | `UID` | CALENDAR | `{}` |       |       |

To support multiple access patterns the following Global Search Indexes (GSI) are defined.

| GSI  | PK                     | SK                     | Description                             |
|------|------------------------|------------------------|-----------------------------------------|
| GSI1 | CALENDAR               | `GROUP`#CALENDAR#`UID` | Retrieve a list of calendars            |
| GSI2 | `GROUP`#CALENDAR#`UID` | `GROUP`#CALENDAR#`UID` | Retrieve a calendar and it's components |



### Calendar Web Components
TBD.
