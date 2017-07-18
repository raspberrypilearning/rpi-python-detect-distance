With your ultrasonic distance sensor connected to your Raspberry Pi, and a new Python file open, you are ready to detect distances.

- First, you need create a `DistanceSensor` object, stating the pins you have connected your distance sensor to.

	```python
	from gpiozero import DistanceSensor
	ultrasonic = DistanceSensor(echo=17, trigger=4)
	```
- You can measure the distance an object is away from the sensor.

	```python
	print(ultrasonic.distance)
	```

- You can also wait for an object to come into range, or out of range.

	```python
	ultrasonic.wait_for_in_range()
	ultrasonic.wait_for_out_of_range()
	```

- You can call a specific function when an object comes into range or out of range.

```python
def do_thing():
    print('Change happened')

ultrasonic.when_in_range = do_thing
ultrasonic.when_out_of_range = do_thing
```
