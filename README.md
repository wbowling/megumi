# megumi
Emulator for Atmel AVR XMEGA microcontrollers

## Requirements

```bash
sudo apt-get install build-essential libboost-dev libboost-program-options-dev
```

## Compile

```bash
CPPFLAGS="-D NDEBUG" make
```

## UART:

```bash
socat -d -d pty,raw,echo=0 pty,raw,echo=0
2018/02/27 15:11:05 socat[3403] N PTY is /dev/pts/2
2018/02/27 15:11:05 socat[3403] N PTY is /dev/pts/3
```

Config file:
```ini
[USARTC0]
link_type=serial
link_path=/dev/pts/3
```

Reading:
```bash
cat < /dev/pts/2
```

Writing:
```bash
echo "hello" > /dev/pts/2
```

## Run
```bash
./megumi -f config.ini program.hex -g
```

```bash
avr-gdb
> target remote :2345
```
