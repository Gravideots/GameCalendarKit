## GameClock

GameClock is the successor of MonoBehaviour and provides the necessary set of methods and events for creating game time.

Can be used without GameCalendar to check time from start to end values.

### Namespace

GameClock contains in GameTime.Clock namespace, don't forget to include it to your header if you use this class separately of GameCalendar.

### Events

* MinuteEndEvent - MinuteEndEvent is a event method which will be launched when game minute ending.
* DayEndEvent -  DayEndEvent is a event method which will be launched when game day ending.

### Methods

* GameClockInit(int startTime, int endTime, float interval) - GameClockInit is an initialization method which set a start values to ticker and add to event TickEvent, method ClockWork. Request three arguments:
  * startTime - from this value it will start tick; 
  * endTime - when clock reach this value DayEndEvent will fired up;
  * interval - this value tell how many seconds will be in one game minute.
* StartClock - StartClock is a method that start clock work.
* PauseClock - PauseClock is a method for pause clock time. Stop only this clock time, Unity time is still work.
* ContinueClock - ContinueClock is a method for continue clock time. Continue from paused value.
