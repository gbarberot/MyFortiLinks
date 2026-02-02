# MyFortiLinks - [FortiOS](https://docs.fortinet.com/product/fortigate/) -  [Back to Root](../readme.md)

### FortiGate CheatSheets

- [Boll.ch CheatSheet FOS 7.6](https://blog.boll.ch/cheatsheet-fortios-v7-6/)
- [InfosecMonkey.com CLI Bible](https://infosecmonkey.com/my-fortigate-fortios-cli-bibleish/)
- [My CLI Cheatsheet](./FortiOS-cli.md)




### Recommended versions

- [Technical Tip: Recommended Release for FortiOS](https://community.fortinet.com/t5/FortiGate/Technical-Tip-Recommended-Release-for-FortiOS/ta-p/227178)
- [Technical Tip: Recommended Release for FortiManager and FortiAnalyzer](https://community.fortinet.com/t5/FortiManager/Technical-Tip-Recommended-Release-for-FortiManager-and/ta-p/231910)

### Logging

- [Technical Tip: How to configure logging to disk on the FortiGate using the GUI or the CLI](https://community.fortinet.com/t5/FortiGate/Technical-Tip-How-to-configure-logging-to-disk-on-the-FortiGate/ta-p/216995)
- [Technical Tip: Hard disk utilization by the FortiGate](https://community.fortinet.com/t5/FortiGate/Technical-Tip-Hard-disk-utilization-by-the-FortiGate/ta-p/195481)
- [Troubleshooting Tip: FortiGate to FortiAnalyzer connectivity](https://community.fortinet.com/t5/FortiAnalyzer/Troubleshooting-Tip-FortiGate-to-FortiAnalyzer-connectivity/ta-p/191833)


### Access internal ressources from Outside

- [Technical Tip: Using Virtual IPs to configure port forwarding](https://community.fortinet.com/t5/FortiGate/Technical-Tip-Using-Virtual-IPs-to-configure-port-forwarding/ta-p/198195)
- [Technical Tip: How to configure SAML authentication for firewall policy with Virtual IP (VIP)](https://community.fortinet.com/t5/FortiGate/Technical-Tip-How-to-configure-SAML-authentication-for-firewall/ta-p/243639)


### VPN Ressources
- [Technical Tip: FortiGate IPsec VPN resource list](https://community.fortinet.com/t5/FortiGate/Technical-Tip-FortiGate-IPsec-VPN-resource-list/ta-p/213560)
- [Technical Tip: Overview of compatible IKE versions, user authentication methods, and FortiGate/FortiClient firmware versions](https://community.fortinet.com/t5/FortiGate/Technical-Tip-Overview-of-compatible-IKE-versions-user/ta-p/420733)
- [Technical Tip: Increasing email Token expiry time](https://community.fortinet.com/t5/FortiGate/Technical-Tip-Increasing-email-Token-expiry-time/ta-p/190638)
- [Technical Tip: How to block IPsec fail connection attempts over a blacklist (ESP IKEv1 or IKEv2, Phase 1 mismatch config and authentication failure)](https://community.fortinet.com/t5/FortiGate/Technical-Tip-How-to-block-IPsec-fail-connection-attempts-over-a/ta-p/411328)

### GenAI & LLM related Features

- [Technical Guide: Selective control & monitoring of GenAI / LLM application traffic with Fortinet Security Fabric](https://community.fortinet.com/t5/FortiGate/Technical-Guide-Selective-control-amp-monitoring-of-GenAI-LLM/ta-p/405240)
- [Doc: Application control support for generative AI 7.6.4](https://docs.fortinet.com/document/fortigate/7.6.0/new-features/679448/application-control-support-for-generative-ai-7-6-4)
    <details>
    <summary>Check Version/updates of App Control GenAI DB</summary>
    
        (FGT)# diagnose autoupdate versions | grep -A 6 GenAI

    Note : if GenAI DB is not up to date, reason could be you have no app control profile enabled on any FW Policy : enable at least one FW rule with App control profile enabled
    </details>
- [Technical Tip: Blocking Chat GPT](https://community.fortinet.com/t5/FortiGate/Technical-Tip-Blocking-Chat-GPT/ta-p/255020)


### 802.1x

- [Using 802.1X on FortiGate interface](https://docs.fortinet.com/document/fortigate/7.6.5/administration-guide/100999/hardware-switch#:~:text=Example%20of%20using%20802.1X%20on%20virtual%20switches)

### Fortilink NAC

- [Troubleshooting Tip: FortiSwitch port flap with laptop connected with wifi/wired using FortiClient EMS tags](https://community.fortinet.com/t5/FortiSwitch/Troubleshooting-Tip-FortiSwitch-port-flap-with-laptop-connected/ta-p/360109)


### VDOM

- [Enable Vdom on FortiGate](https://docs.fortinet.com/document/fortigate/7.6.5/administration-guide/32293/general-configurations)
    <details>
    <summary>Example of VDOM</summary>
    
        (FGT)# 
        config system global
            set vdom-mode multi-vdom
            set edit-vdom-prompt enable
        end
    </details>

- [Multitenancy, VDOMS and Fortiswitches](https://docs.fortinet.com/document/fortiswitch/7.6.5/fortilink-guide/801172)