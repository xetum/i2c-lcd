# LCD I2C driver (1602/2004/..)

This is a Ruby driver for the 2004A/1602 LCD display with I2C adapter
(tested with PCF8574T),
forked from [i2c-ss1602](https://github.com/nerab/i2c-ss1602).

The original i2c-ss1602 was partially ported from [raspi-gpio](https://github.com/paulbarber/raspi-gpio/blob/master/lcd_display.py).

## Installation

Add this line to your application's Gemfile:

```
gem 'i2c-lcd'
```

And then execute:

```
$ bundle
```

Or install it yourself as:

```
$ gem install i2c-lcd
```

## Usage

```ruby
require 'i2c/drivers/lcd'
display = I2C::Drivers::LCD::Display.new('/dev/i2c-1', 0x27, rows=20, cols=4)
display.clear
display.text('Hello', 0)
display.text('World', 1)
display.text('Line3', 2)
display.text('Line4', 3)
```

'rows' and 'cols' options are optional. The default value is 20 and 4.
