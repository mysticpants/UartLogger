# UartLogger 1.0.0

The UartLogger class is an Electric Imp device side library to allow for writing logs on uart. This is helpful when running an Imp offline.

## Class Usage

### Constructor: UartLogger(uart)

The UartLogger class is instantiated with a configured uart object. The class only needs the TX line.

```squirrel
uart <- hardware.uart12;
uart.configure(9600, 8, PARITY_NONE, 1, NO_CTSRTS);
logs <- UartLogger(uart);
```

## Class Methods

## log(msg)

Writes the supplied message to the uart and to server.log if the device is connected. The current timestamp is prepended to the message.

```squirrel
logs.log("test");
// Output: "2016-08-19 10:21:00    test"
```

## error(msg)

Writes the supplied message to the uart and to server.error if the device is connected. The current timestamp and "[ERROR]" are prepended to the message.

```squirrel
logs.error("test");
// Output: "2016-08-19 10:21:00    [ERROR] test"
```

# License

The UartLogger class is licensed under the [MIT License](https://github.com/mysticpants/UartLogger/LICENSE)
