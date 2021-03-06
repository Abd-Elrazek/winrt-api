---
-api-id: M:Windows.Gaming.Input.FlightStick.FromGameController(Windows.Gaming.Input.IGameController)
-api-type: winrt method
---

<!-- Method syntax.
public FlightStick FlightStick.FromGameController(IGameController gameController)
-->

# Windows.Gaming.Input.FlightStick.FromGameController

## -description

Returns the given game controller as a flight stick.

## -params

## -param gameController

The game controller to be returned as a flight stick.

## -returns

The flight stick that was returned from the given game controller.

## -remarks

This method checks if the provided game controller has a flight stick implementation, and if so, it returns that implementation. You might use this method if you want to first get the controller as a [RawGameController](rawgamecontroller.md), and then see if it can be used as a **FlightStick**&mdash;if so, you can use a default control scheme for flight sticks, otherwise you can let the player do their own input mapping.

## -see-also

* [Windows.Gaming.Input.IGameController](igamecontroller.md)

## -examples

In the following example, the app gets the first available [RawGameController](rawgamecontroller.md) object, and tries to access this game controller via the **FlightStick** class:

```cpp
FlightStick^ flightStick;

if (RawGameController::RawGameControllers->Size > 0)
{
    RawGameController^ rawGameController = 
        RawGameController::RawGameControllers->GetAt(0);
        
    flightStick = FlightStick::FromGameController(rawGameController);
}

if (flightStick != nullptr)
{
    // Assign a standard button mapping to this controller.
}
```