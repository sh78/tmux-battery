`tmux-battery`
==============

Rather simple CLI to show the battery level in tmux. Mac specific.

![screenshot](https://cloud.githubusercontent.com/assets/291371/3788012/17d75966-1a4c-11e4-8c16-2a46bba2bd1b.png)

You can see the checkmark on the left of the date.

This is written in C using CoreFoundation and IOKit.

## Usage
`tmux-battery [[WHEN_FULL]] [[WHEN_DRAINING]] [[WHEN_CHARGING]] [[THRESHOLD]]`

By default, it outputs:
- Full battery, plugged in: a checkmark
- Charging battery, plugged in: an up arrow and the percentage
- Discharging battery, not plugged in: a down arrow and the percentage
- Below the threshold (10% by default): a down arrow, the percentage, and an exclamation point

Optionally, pass in three of your own strings to use instead of the default symbols above and a
custom `threshhold` value. You can even pass in emojis!

    tmux-battery 🔋 🔌 ⚡️ 15
    # => "⚡️ 14%!"
    # => "🔌 16%"
    # => "🔋"
