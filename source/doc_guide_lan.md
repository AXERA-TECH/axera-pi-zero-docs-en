# GPIO/I2C/SPI and other communication interface operation examples

## Read and write operations on GPIO

1. Use the echo command on the console to determine the GPIO number to be operated.
```
echo N > /sys/class/gpio/export //It will be generated after export
/sys/class/gpio/gpioN directory
```

2. Use the echo command on the console to set the GPIO direction.
```
echo in > /sys/class/gpio/gpioN/direction
echo out > /sys/class/gpio/gpioN/direction
```

3. Use the cat or echo command on the console to view the GPIO input value or set the GPIO output value
```
echo N > /sys/class/gpio/export //It will be generated after export
/sys/class/gpio/gpioN directory
cat /sys/class/gpio/gpioN/value //View input value
echo 0 > /sys/class/gpio/gpioN/value //output low
echo 1 > /sys/class/gpio/gpioN/value //Output high
```
```
For example, set GPIO1_17 direction:
echo 49 > /sys/class/gpio/gpioN/export
echo in > /sys/class/gpio/gpio49/direction //Input enable
cat /sys/class/gpio/gpio49/value //View input value
echo out > /sys/class/gpio/gpio49/direction //Output enable
echo 0 > /sys/class/gpio/gpio49/value //output low
echo 1 > /sys/class/gpio/gpio49/value //Output high
cat /sys/class/gpio/gpio49/direction //View the GPIO direction. The level values ​​of GPIO are only 0 and 1. 0 is low level and 1 is high level.
```

4. Use the echo command on the console to unexport the GPIO number of the operation.
```
echo N > /sys/class/gpio/unexport
```

GPIO is divided into #0, #1, #2, and #3, and each group has 32 GPIOs. Make the following agreement that N is the number of the GPIO, and P is the group number. The value range is 0, 1, 2, and 3. You can get N=p*32+offset.
Taking GPIO1_17 as an example to calculate the GPIO number, we can know that P=1, offset is 17, and N=1*32+17=49.