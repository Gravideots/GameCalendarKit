## Events
GameTimeKit contain six events in three class and four type of Event Object. You can use them by add your method to event like on example below:

#### GameCalendar Events
* CalendarDayEndEvent - this event will invoke all contained method after the working day is over. Transmit new GameClockEventObject.
* CalendarEventStarted - this event will invoke all contained method if GameCalendar will find some event on current time and date. Transmit new GameCalendarEventObjectList.
* CalendarEventEnded - same as previous but will invoke on end events date.

#### GameClock Events
* MinuteEndEvent - this event will invoke all contained method when the game minute is over and transmit new GameClockEventObject.
* DayEndEvent - this event will invoke all contained method when the working day is over and transmit new GameClockEventObject.

#### Ticker Events
* TickEvent - this event will invoke all contained method when the InvokeRepeating Unity method will invoke and transmit new TickEventObject.

### Events Objects
Event Object is a class successor of EventArgs, that contain some custom serialized(or not) fields whit all base and custom information such as:
* Status
* DateTime
* Title
* etc

some of Event Object have a partial keyword, that mean you can add you realization to this object.

#### TickEventObject

Ticks object have a Constructor method:

```
public TickEventObject(bool status, int curentTickIteration, int curentIntervalIteration)
{
    _status = status;
    _curentTickIteration = curentTickIteration;
    _curentIntervalIteration = curentIntervalIteration;
}
```

and contain base property which care information about current tick, such as:

* Status
* CurentIntervalIteration
* CurentTickIteration

```
public bool Status
{
    get
    {
        return _status;
    }
}

public int CurentIntervalIteration
{
    get
    {
        return _curentIntervalIteration;
    }
}

public int CurentTickIteration
{
    get
    {
        return _curentTickIteration;
    }
}
```
