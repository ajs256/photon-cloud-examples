# photon-cloud-examples

Lately, I've really been loving the [Particle Photon](https://store.particle.io/collections/gen-2/products/photon), mostly because it has a cloud platform that _just works_. Here's my best explanation of everything it can do!

Note that these were written for the Photon but will probably work with other Particle boards.

## Variables
These are probably the simplest. You define a variable with `Particle.variable`, then it will automatically sync with the cloud.
### Use:
```cpp
Particle.variable("variable", variable);
```
Pass in the name that the cloud will see and use as a string, and then the name of the variable used in the code. Variables can be `int`s, `bool`s, `String`s, or `double`s. Notably, `floats` cannot be used.
Names are limited to 64 characters.
### Full Example
```cpp
bool circuitClosed = false;


void setup() {
    Particle.variable("circuitClosed", circuitClosed);
    pinMode(D2, INPUT_PULLUP);
}

void loop() {
    if(digitalRead(D2) == LOW) {
        circuitClosed = true;
    } else {
        circuitClosed = false;
    }
}
```
If a wire is connected between pin D2 and any GND pin, the `circuitClosed` variable should show up as true on [the console](console.particle.io).

Variables are great when you need to check a value on a device from the cloud or an app. They aren't so great when you want to do something on the board form the cloud. For that, you would use a function.

## Functions
WIP
## Events
WIP
