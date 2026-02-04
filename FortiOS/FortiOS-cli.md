# MyFortiLinks - [FortiOS](https://docs.fortinet.com/product/fortigate/) -  [Back to Root](../readme.md)

### My CLI CheatSheet

<details>
<summary>CLI Command Alias</summary>

    (FGT)# config system alias
        edit "ddot"
        set command "diagnose switch-controller switch-info 802.1X ACCESS-01 port2"
        next
    end
    (FGT)# alias ddot
</details>

<details>
<summary>Packet sniffer</summary> 

    (FGT)# diagnose sniffer packet any 'host 10.1.10.20 and !port 443' 4 100 l 0
    
Remember: ASIC offloading can "hide" packets, you could have to disable auto-asic-offload on FW rule

