- Mid circuit measurements with a weird synatx
```
output = qml.measure()

qml.cond(output > 0, RX)(angle, wires=0)
```