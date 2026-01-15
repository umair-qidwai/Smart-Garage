# Smart-Garage
Make a normal garage door opener smart, using an ESP32 and a Relay. (Make sure to use a 3.3v Relay with an ESP32).

### This config is for Homeassistant currently, but you could probably use arduino code or similar as well to control this.

### The Build instructions are below, The code for the ESP32 is a yaml file for ESPHome.

## Build Instructions:
- Buy an esp32 or esp8266, and a relay. Here are the links (non-affiliate):

[ESP32 - Amazon](https://www.amazon.com/ESP-WROOM-32-Development-Microcontroller-Integrated-Compatible/dp/B08D5ZD528/ref=sr_1_3?crid=2Q4D8H26THTUZ&dib=eyJ2IjoiMSJ9.XBINg-sjhfF_gUtnMiKGjiaUVHZzlth3MSG3HA94qR_-kqokqweLRBdfmyBPh-86Mt8noI2L5vTV1s1tN4sPNIG1cyDPkht7ifMeDQ1IDXo79iIS77LZtZbpMFcHsMQKDa6FOHn1xN28rNfC_hrJ4gBdUQEnwVngkVqyhTGaoDY8bz1oqBjB9momXC--vevjJiNF33y2S8AFlE30iIb7cGJ2DQsiVh4ujhhrqXIxA4g.PlpdDZ1oZ9Nf8q1NzM3jKrD_1hRGygzUFIaNNKXwc0o&dib_tag=se&keywords=esp32&qid=1766063752&sprefix=esp3%2Caps%2C159&sr=8-3)

[ESP8266 - Amazon](https://www.amazon.com/Hosyond-Wireless-Development-Compatible-Micropython/dp/B09SPWYS4B/ref=sr_1_5?crid=279RRF20TOKRX&dib=eyJ2IjoiMSJ9.gJShu3rQeKD8EK_mYUdf6X_pH-K5K_92i8HvzqK1FLfFdVL7VG5uZKo7qls8mvAKpXfuRwAT7t4CUjPP9FVe4g5YJ1QEEvuTtAwUl-Pv1QmUeqK-brL16z6dzfhnw-bnPmizaDch9_bE1EPuRG5cgaNiAYmAgvzz6SNYHTJ3bZC5lkyu9BSs7U2-SaLc_UNrzECpFzldrcFbK4Z9PFY5CaSu3MGvt8rGwbf3kA9SYOY.UEdLThGfA2mXoLH83AEBReHlo8Yzah_lKXgrk_qspu0&dib_tag=se&keywords=esp8266&qid=1766063849&sprefix=esp8266%2Caps%2C147&sr=8-5&th=1)

[Relay - Amazon](https://www.amazon.com/MTDELE-Channel-Optocoupler-Isolated-Compatible/dp/B0D8PSX9WL/ref=sr_1_5?crid=T7FV97M5PQ22&dib=eyJ2IjoiMSJ9.aQ-rgB_Q-5VmyzSnoas2Vrk0XTuFuz46OYdsepqKNJBPCmp9GscxK05bx6FvWIyF3VosFwATjGJEkUe1w7Ktm23zz6EJGS_aE1ngtvTQHeAQhvE2-kxxD9ZJDcj_6wgukUszOVQqyK_HjLfVASZUpxQ9Q6Gk3FeCZv62fQSTphh-6MAsujjDU3jqO9QJfMypiiWMJEbUktOY_IPpgRf65ihcQyWo8UqJg-8Y5yjYUYQ.-D6QtplPn3JyB3mDQrC6OuEjCIil6HLPiM8nR4wpc0I&dib_tag=se&keywords=3.3v+relay&qid=1768497789&sprefix=3.3v+rela%2Caps%2C155&sr=8-5)

- You will also need some wires, depending on how you plan to wire this (solder or pin connectors)

### Step 1:
- Connect the VCC pin from the realy to the 3v3 (3.3v) pin on the ESP
- Connect the IN pin from the relay to pin D4 on the ESP32 (This can be changed if you are willing to edit the code)
- Connect the GND pin from the relay to the GND (Ground) pin on the ESP
- Refer to the "ESP32 Wiring.png" image above

- ### Step 2
- Flash the ESP with ESPhome using Homeassistant or https://web.esphome.io/
- Use the file I have provided above, you should only need the code after the line "captive_portal:", everything else should already be there, with your credentials

### Step 3
- Connect the other side of the relay (The NO and COM side) to your Garage door opener
- OPTION 1: If you have an older garage door opener, that has a "push button switch" that simply completes the circuit (A normal switch), then you can wire this directly into your door opener where the push button switch wires connect. (Same 2 contacts)
- OPTION 2: If you have a newer garage door opener, that has a "push button switch" that sends a signal, not just completes a circuit, then you can wire this esp to an old garage remote. 99% of these have normal push button switches. You will need to pair this remote with your garage, make sure it works, and then wire the other end of the relay to this switch instead. Make sure to take the battery out when wiring, so the garage door doesn't keep opening.
- Make sure to connect the NO and COM port from the Relay to whichever opion you are choosign above. The orientation of those doesn't matter, it should work both ways.
