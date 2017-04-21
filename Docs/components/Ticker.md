## Ticker

Ticker is the successor of MonoBehaviour and provides the necessary set of methods and events for make timer counting from A to B value.

Can be used wthout GameCalendar and GameClock.

### Namespace

Ticker contains in GameTime.TickerUtil namespace, don't forget to include it to your header if you use this class separately of GameClock or GameCalendar.

### Events

* TickEvent - TickEvent is a event method which will be launched when tick counted from private method OnTimedEvent().

### Methods

* TickerInit(int tickIterations, float intervalInSeconds, int maxIterations) - TickerInit is a initiated method which set a start values to ticker. Request three arguments:
  * int tickIterations - How many ticks will be counted in one Iteration;
  * intervalInSeconds - The time interval between tick;
  * maxIntervalIterations - this value tell how many seconds will be in one game minute.
* StartNewTimer - StartNewTimer is a method to start new timer with initial values. Before start new, it will stop previous one if it already launched.
* StartTimer - StartTimer is a method to continue timer again with _currentTickIteration + 1. If current iteration == maxIterations it will brake execution and fireup Tick event with false and 0,0 arguments.
* StopTimer -  StopTimer is a method to stop timer. Also will fireup Tick event whit current tick and iteration.
* PauseTimer - PauseTimer is a method to stop timer on current without any message.
