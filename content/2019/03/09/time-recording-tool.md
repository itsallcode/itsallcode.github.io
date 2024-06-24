---
title: "Time Recording Tool"
date: 2019-03-09T20:49:02+02:00
draft: false
params:
    author: Christoph 
---

To keep track of my working time I wrote a small time recording tool called White Rabbit. You can find it at [https://github.com/itsallcode/white-rabbit](https://github.com/itsallcode/white-rabbit).

# Features

- Simple text user interface
- Records begin, end and interruption of your working day
- Data storage in human-readable json files, one file per month
- Manual interruptions: press `i` to start and stop interruptions
- Supports weekend, public holiday, vacation, flex time and sickness (see json example)
- Reporting of total overtime: press `r`
- Automatic update in the background (press `u` to update manually): just keep it running and it will record your working time
    - Start of work is detected via
        - Program start
        - Computer resumes from sleep in the morning
    - End of work is detected via
        - Program shutdown
        - Computer sleeps for the rest of the day
- Interruptions added when computer sleeps for more than 2 minutes
- Assumptions:
    - Working time of 8h Monday to Friday
    - Mandatory break of 45 minutes after 6 hours of working

# Architectural descisions

The architecture separates business logic (sub-project logic) from the user interface (textui). This allows you to add additional user interfaces e.g. using JavaFX or Swing.

We use JSON for storage because this enables the user to manually make changes (e.g. add a sick day).  So we can keep the user interface as simple as possible.

# Example data file

```json
{
    "year": 2019,
    "month": "MARCH",
    "days": [
        {
            "date": "2019-03-01",
            "begin": "08:00:00",
            "end": "17:00:00",
            "comment": "First working day (type WORK is optional)"
        },
        {
            "date": "2019-03-04",
            "type": "VACATION",
            "comment": "Vacation day, no change to working time"
        },
        {
            "date": "2019-03-05",
            "type": "FLEX_TIME",
            "comment": "Flex time, deducts 8h from your time"
        },
        {
            "date": "2019-03-06",
            "type": "HOLIDAY",
            "comment": "A public holiday, not working"
        },
        {
            "date": "2019-03-07",
            "type": "SICK",
            "comment": "Sick day, no change to working time"
        },
        {
            "date": "2019-03-08",
            "begin": "08:00:00",
            "end": "18:30:00",
            "interruption": "PT1H20M",
            "comment": "1h 20min of interruption"
        },
        {
            "date": "2019-03-09",
            "type": "WEEKEND",
            "comment": "Saturday and Sunday automatically detected, no need to add them here."
        }
    ]
}
```

# Example report

```
2019-03-01 Fri WORK      08:00 - 17:00 break: 00:45, working time: 08:15, overtime: 00:15, Acc. overtime: 00:15, First working day (type WORK is optional)
2019-03-04 Mon VACATION                break: 00:00, working time: 00:00, overtime: 00:00, Acc. overtime: 00:15, Vacation day, no change to working time
2019-03-05 Tue FLEX-TIME               break: 00:00, working time: 00:00, overtime: -08:00, Acc. overtime: -07:45, Flex time, deducts 8h from your time
2019-03-06 Wed HOLIDAY                 break: 00:00, working time: 00:00, overtime: 00:00, Acc. overtime: -07:45, A public holiday, not working
2019-03-07 Thu SICK                    break: 00:00, working time: 00:00, overtime: 00:00, Acc. overtime: -07:45, Sick day, no change to working time
2019-03-08 Fri WORK      08:00 - 18:30 break: 00:45, interr.: 01:20, working time: 08:25, overtime: 00:25, Acc. overtime: -07:20, 1h 20min of interruption
2019-03-09 Sat WEEKEND                 break: 00:00, working time: 00:00, overtime: 00:00, Acc. overtime: -07:20, Saturday and Sunday automatically detected, no need to add them here.
Total overtime: PT-7H-20M
```