## GameCalendar

GameCalendar is the successor of MonoBehaviour and provides the necessary set of methods and events for creating game calendar and work with events collections.

### Namespace

GameCalendar contains in main GameTime namespace, don't forget to include it to your header.

### Fields

* BaseEventsCollection -  Pregenerated events ScriptableObject, you can find generator in menu GameTime -> Event Object Creator.  
* StartYear, StartMonth, StartDay - Initial value. Here you can choose the year, month and date from which the time begins in the game.
* StartWorkTime, EndWorkTime - Initial value. Here you can choose the StartWorkTime and EndWorkTime.
* MinutesScale - This value provides the ability to set the number of seconds in one game minute. The minimum stable and guaranteed working value is one second for now.

### Events

* CalendarDayEndEvent - CalendarDayEndEvent is event method which will be launched at the end of the working day.
* CalendarEventStarted - CalendarEventStarted is event method which will be launched when and if new event started.
* CalendarEventEnded - CalendarEventStarted is event method which will be launched when any event ended.

### Methods

* StartNewDay - StartNewDay is a method for starting new day. First day also start here.
* RestartDay - RestartDay is a method for restart current day.
* PauseDay - PauseDay is a method for pause calendar time. Stops only calendar, not the all game.
* ContinueDay - ContinueDay is a method for continue calendar time if it was paused. Continue tick from paused moment.
* GetCurrentDate - GetCurrentDate return current game date.
* CreateEvent([GameCalendarEventObject](./Events.md) newEvent) - CreateEvent put new GameCalendarEventObject object to calendar events collection.
* GetAllEventsByDate(DateTime date) - GetAllEventsByDate return all GameCalendarEventObject that matches requested date.
* GetAllEvents - GetAllEvents return all GameCalendarEventObject.
* ChangeTimeScale(float timeScale) - ChangeTimeScale change global timeScale to transmitted value.
