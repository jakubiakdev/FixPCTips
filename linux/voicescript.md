# Destroy\_your\_mic\_quality.sh

Problem: You want to worsen your microphone quality, for these times that you really don't want to answer the question on online classes. Well, this scirpt might be just for you! This script depends on `pactl`.

The actual script

```text
#!/bin/sh
while :
do
        pactl set-source-volume alsa_input.pci-0000_08_00.4.analog-stereo 99999999% //Sets your microphone volume to ridiculous value
        sleep 0.0$((RANDOM)) //Wait for random amount of time to simulate lag
        pactl set-source-volume alsa_input.pci-0000_08_00.4.analog-stereo 0% // Mutes your microphone
        sleep 0.0$((RANDOM)) //Wait for random amount of time to simulate lag
done                  
```

## Notes

To use this scirpt you might need to change the input device from`alsa_input.pci-0000_08_00.4.analog-stereo` To your own device from `pactl list short sources`





