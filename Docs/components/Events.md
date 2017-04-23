# Events
GameTimeKit contain six events in three class and four type of Event Object. You can use them by add your method to event like on example below:

Initialize GameCalendar in Calendar variable:

```
public GameCalendar Calendar;
```

create method DayOver that will wait when event CalendarDayEndEvent invoke.

```
private void DayOver(object source, GameClockEventObject clockObject)
{
    print("Day is over, current time is: " + clockObject.Hour + ":" + clockObject.Minute);
}
```

add DayOver to Calendar.CalendarDayEndEvent event:
```
void Start()
{
    Calendar.CalendarDayEndEvent += DayOver;
}
```

after invoke CalendarDayEndEvent, print method inside DayOver method will execute.

### GameCalendar Events
* CalendarDayEndEvent - this event will invoke all contained method after the working day is over. Transmit new GameClockEventObject.
* CalendarEventStarted - this event will invoke all contained method if GameCalendar will find some event on current time and date. Transmit new GameCalendarEventObjectList.
* CalendarEventEnded - same as previous but will invoke on end events date.

### GameClock Events
* MinuteEndEvent - this event will invoke all contained method when the game minute is over and transmit new GameClockEventObject.
* DayEndEvent - this event will invoke all contained method when the working day is over and transmit new GameClockEventObject.

### Ticker Events
* TickEvent - this event will invoke all contained method when the InvokeRepeating Unity method will invoke and transmit new TickEventObject.

### Events Objects

Event Object is a class successor of EventArgs, that contain some custom serialized(or not) fields whit all base and custom information such as:
* Status
* DateTime
* Title
* etc

some of Event Object have a partial keyword, that mean you can extend class and add you own realization.


### GameCalendarEventObject

Constructor method:

```
public GameCalendarEventObject(DateTime dateStart, DateTime dateEnd, string title)
{
    _dateStart = dateStart.ToString();
    _dateEnd = dateEnd.ToString();
    _title = title;
}
```

Base property which care information about current event, such as:

```
public DateTime DateStart
{
    get
    {
        return DateTime.Parse(_dateStart); ;
    }
}

public DateTime DateEnd
{
    get
    {
        return DateTime.Parse(_dateEnd); ;
    }
}

public string Title
{
    get
    {
        return _title;
    }
}
```

#### Partial example

This object has a partial keyword that give you a possibility to extend current class and create your own event object.

```
public partial class GameCalendarEventObject
{
    public GameCalendarEventObject(DateTime dateStart, DateTime dateEnd, string title, string text)
    {
        _dateStart = dateStart.ToString();
        _dateEnd = dateEnd.ToString();
        _title = title;
        _text = text;
    }

    [SerializeField]
    string _text;

    public string Text
    {
        get
        {
            return _text;
        }
    }
}
```
this example add new serialized field and property Text to base class.

### GameClockEventObject

Constructor method:

```
public GameClockEventObject(bool status, int hour, int minute)
{
    _status = status;
    _hour = hour;
    _minute = minute;
}
```

Base property which care information about current time and status, such as:

```
public bool Status
{
    get
    {
        return _status;
    }
}

public int Hour
{
    get
    {
        return _hour;
    }
}

public int Minute
{
    get
    {
        return _minute;
    }
}
```

### TickEventObject


Constructor method:

```
public TickEventObject(bool status, int curentTickIteration, int curentIntervalIteration)
{
    _status = status;
    _curentTickIteration = curentTickIteration;
    _curentIntervalIteration = curentIntervalIteration;
}
```

and contain base property which care information about current tick, such as:

* Status - when ticks iteration is over this value will be false, otherwise it's true.
* CurentIteration - current iteration of ticker,
* CurentTick

```
public bool Status
{
    get
    {
        return _status;
    }
}

public int CurentIteration
{
    get
    {
        return _curentIteration;
    }
}

public int CurentTick
{
    get
    {
        return _curentTick;
    }
}
```
