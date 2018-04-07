# SandTimer

This library allow you to set and use timers easily over Arduino platform. The implementation doesn't use delay function, and it is very fast. This is very important if you want your board to keep doing things in the "background" while using timer.

## Usage

1. Include SandTimer.h in your code 

2. Create a new SandTimer instance

```
SandTimer my_timer;
```

2. Start the timer, and do something when it's finished

```
void loop()
{
  ...
  ...
  my_timer.start(1000);
  if (my_timer.finished())
    Serial.println("time is up");
  ...
  ...
}
```

Although start() is invoked inside loop(), timer will only start once. Only after timer is finished, start() method will cause it to start again. If you wish to start timer again before it's finished, use startOver();
