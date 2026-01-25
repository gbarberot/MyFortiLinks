# MyFortiLinks - [FortiSwitch](https://docs.fortinet.com/product/fortiswitch/) - [Back to Root](../readme.md)

## FortiSwitch

## FortiLink

## Network Design tips
- [Doc: Determining the network topology](https://docs.fortinet.com/document/fortiswitch/7.6.5/fortilink-guide/617516/determining-the-network-topology)
- [Doc: HA-mode FortiGate units managing a stack of several FortiSwitch units](https://docs.fortinet.com/document/fortiswitch/7.6.5/fortilink-guide/801190/ha-mode-fortigate-units-managing-a-stack-of-several-fortiswitch-units)
- [Doc: Switch redundancy with MCLAG](https://docs.fortinet.com/document/fortiswitch/7.6.5/fortilink-guide/780635/switch-redundancy-with-mclag)
- [Doc: Multi-tiered MCLAG with HA-mode FortiGate units](https://docs.fortinet.com/document/fortiswitch/7.6.5/fortilink-guide/801194/deploying-mclag-topologies#Three-ti)

## Transcievers & SFP
- [Troubleshooting Tip: SFP/SFP+ transceivers port/fiber link is not coming up](https://community.fortinet.com/t5/FortiSwitch/Troubleshooting-Tip-SFP-SFP-transceivers-port-fiber-link-is-not/ta-p/193940)
- [Technical Tip: How to get details of a transceiver connected in a managed FortiSwitch from the FortiGate CLI](https://community.fortinet.com/t5/FortiGate/Technical-Tip-How-to-get-details-of-a-transceiver-connected-in-a/ta-p/348457)
- <details>
  <summary>Get RX power of an sfp from Switch CLI</summary>
  
        (FGT)# get switch modules status <port#>
  </details>


## 802.1x

### Authentication

- [Troubleshooting Tip: Configure and troubleshoot 802.1x authentication on a Managed FortiSwitch](https://community.fortinet.com/t5/FortiSwitch/Troubleshooting-Tip-Configure-and-troubleshoot-802-1x/ta-p/194605)
- [Technical Tip: FortiSwitch 802.1x authentication behaviour when multiple authentication radius servers are configured](https://community.fortinet.com/t5/FortiSwitch/Technical-Tip-FortiSwitch-802-1x-authentication-behaviour-when/ta-p/384705)
- [Changing the order and priority of MAB and EAP 802.1X authentication](https://docs.fortinet.com/document/fortiswitch/7.6.5/fortilink-guide/756049/fortiswitch-security-policies#Test:~:text=end-,Changing%20the%20priority%20of%20MAB%20and%20EAP%20802.1X%20authentication,-802.1X%20authentication%20and)
    <details>
    <summary>Show Example</summary>

        config switch-controller security-policy 802-1X
            edit "FNAC_802.1x_MAC"
                set security-mode 802.1X-mac-based
                set user-group "FNAC-Radius-GRP"
                set mac-auth-bypass enable
                set auth-order {dot1x-mab | mab-dot1x | mab }   <---------this
                set auth-priority {legacy | dot1x-mab | mab-dot1x}   <---------this
                set open-auth disable
                set eap-passthru enable
                set eap-auto-untagged-vlans enable
                set guest-vlan disable
                set guest-auth-delay 30
                set auth-fail-vlan enable
                set auth-fail-vlan-id "FNAC_ISOL_201"
                set framevid-apply enable
                set radius-timeout-overwrite disable
                set policy-type 802.1X
                set authserver-timeout-vlan disable
                set authserver-timeout-tagged disable
                set dacl disable
            next
        end
    </details>


### Troubleshooting Commands

 -  <details>
    <summary>Get 802.1x status of a Port on FortiSwitch Managed by FortiGate</summary>
    
        (FGT)# diagnose switch-controller switch-info 802.1X ACCESS-SW01 port2 
        
        /Example :
        Site81-FW01 # diagnose switch-controller switch-info 802.1X ACCESS-SW01 port2
        Managed Switch : ACCESS-SW01
        port2 : Mode: mac-based (mac-by-pass enable) 
            Link: Link up
            Port State: authorized: (  ) 
            Dynamic Allowed Vlan list: 20
            Dynamic Untagged Vlan list: 20
            EAP pass-through : Enable
            Auth Order : MAB-dot1x
            Auth Priority : Legacy
            EAP egress-frame-tagged : Enable
            EAP auto-untagged-vlans : Enable
            Dynamic Access Control List : Disable
            Quarantine VLAN (4093) detection : Enable
            Native Vlan : 202
            Allowed Vlan list: 20,202,4093
            Untagged Vlan list: 20,4093
            Guest VLAN :
            Auth-Fail Vlan : 201
            AuthServer-Timeout Vlan :
            AuthServer-Timeout Tagged Vlan :             LLDP Voice Vlan :

            Switch sessions 2/240,     Local port sessions:1/20,   Client limit:20:
            Client    MAC        Type    Traffic-Vlan  Dynamic-Vlan
            f0:de:f1:d1:35:a9     802.1x          202     20

            Sessions info:
            f0:de:f1:d1:35:a9     Type=802.1x,TLS,state=AUTHENTICATED,etime=9,eap_cnt=17 params:reAuth=3600
            user="host/DESKTOP-T520.selab.barberot.org",security_grp="FNAC-Radius-GRP",radsec="disable":tunnel_id="-1", fortinet_grp=""
        Site81-FW01 #   
    </details>

 -  <details>
    <summary>Get 802.1x status of a Port on Standalone FortiSwitch</summary>

        (FSW)# diagnose switch 802-1x status port2 
    </details>




