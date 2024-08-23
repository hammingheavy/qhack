- error can be input in the form of a dictionary 

```
error_dict = {0: 'PauliX', 1: 'PauliY', 2: 'PauliZ'}

def error(error_key, qubit):
    """Defines the error that is induced in the circuit.

    Args:
        error_key (int): An integer associated to the type of error (Pauli X, Y, or Z)
        qubit (int): The qubit that the error occurs on.
    """
    getattr(qml, error_dict[error_key])(qubit)
```

- qml.broadcast can be used to apply multiple gates at once (if they form a nice pattern)

```
qml.broadcast(qml.Hadamard, wires=[0, 3, 6], pattern="single")
qml.broadcast(qml.CNOT, wires=[0, 1, 3, 4, 6, 7], pattern="double")
```