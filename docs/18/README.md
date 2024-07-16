# GL.Inet Slate plus as a home wifi router

I'm searching for a wifi router that is supported by openWRT
and got a toggle button that I can use WIFI AP on/off (I don't want
to use wifi to much at home to limit screen time).

The GL.Inet Slate plus seems interesting.

- It got a toggle switch
- Support openWRT[^1] with
  enough RAM [^2]
- As a USB 3.0, can easily connect an external drive
- Not that expensive (80 USD on alibaba express)
- WiFi 5 (don't need 6 for home usage)

## Add script for toggle button wifi

- Connect to router as SSH 
- Go to `/etc/gl-switch.d`
- Add the following script

```bash
#!/bin/sh

# 2023-07-25
# /etc/gl-switch.d/
# uci show wireless
# source: https://forum.gl-inet.com/t/feature-req-wifi-on-off-with-side-switch/2896/41

action=$1

if [ "$action" = "on" ]; then
        uci set wireless.default_radio0.disabled='0'
        uci set wireless.default_radio1.disabled='0'
        uci commit wireless
        wifi reload
        logger -p notice -t wifi-toggle "radios enabled"
fi

if [ "$action" = "off" ]; then
        uci set wireless.default_radio0.disabled='1'
        uci set wireless.default_radio1.disabled='1'
        uci commit wireless
        wifi reload
        logger -p notice -t wifi-toggle "radios disabled"
fi

exit 0
```

- Make the script executable
- Note: Comment radio0 or radio1 if you only want
to enable 2.4Ghz or 5Ghz

## References

<https://www.gl-inet.com/products/gl-a1300/>
<https://forum.gl-inet.com/t/feature-request-side-button-to-toggle-wifi-on-off-on-dual-radio-devices/32427/2>
[^1]: <https://openwrt.org/toh/gl.inet/gl-a1300>
[^2]: <https://openwrt.org/toh/recommended_routers>
