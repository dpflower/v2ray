# v2ray

bash <(curl -s -L https://raw.githubusercontent.com/dpflower/v2ray/master/install.sh)




https://github.com/v2fly/fhs-install-v2ray

https://intmainreturn0.com/v2ray-config-gen/#

{
        "log": {
                "access": "/var/log/v2ray/access.log",
                "error": "/var/log/v2ray/error.log",
                "loglevel": "warning"
        },
        "inbounds": [
                {
                        "port": 999999,
                        "protocol": "vmess",
                        "settings": {
                                "clients": [
                                        {
                                                "id": "ee558a23-b697-4d09-1326-a34a2006eaa2",
                                                "level": 1,
                                                "alterId": 233
                                        }
                                ]
                        },
                        "streamSettings": {
                                "network": "tcp"
                        },
                        "sniffing": {
                                "enabled": true,
                                "destOverride": [
                                        "http",
                                        "tls"
                                ]
                        }
                }
                //include_ss
                //include_socks
                //include_mtproto
                //include_in_config
                //
        ],
        "outbounds": [
                {
                        "protocol": "freedom",
                        "settings": {
                                "domainStrategy": "UseIP"
                        },
                        "tag": "direct"
                },
                {
                        "protocol": "blackhole",
                        "settings": {},
                        "tag": "blocked"
        },
                {
                        "protocol": "mtproto",
                        "settings": {},
                        "tag": "tg-out"
                }
                //include_out_config
                //
        ],
        "dns": {
                "servers": [
                        "https+local://8.8.8.8/dns-query",
                        "8.8.8.8",
                        "1.1.1.1",
                        "localhost"
                ]
        },
        "routing": {
                "domainStrategy": "IPOnDemand",
                "rules": [
                        {
                                "type": "field",
                                "ip": [
                                        "0.0.0.0/8",
                                        "10.0.0.0/8",
                                        "100.64.0.0/10",
                                        "127.0.0.0/8",
                                        "169.254.0.0/16",
                                        "172.16.0.0/12",
                                        "192.0.0.0/24",
                                        "192.0.2.0/24",
                                        "192.168.0.0/16",
                                        "198.18.0.0/15",
                                        "198.51.100.0/24",
                                        "203.0.113.0/24",
                                        "::1/128",
                                        "fc00::/7",
                                        "fe80::/10"
                                ],
                                "outboundTag": "blocked"
                        },
                        {
                                "type": "field",
                                "inboundTag": ["tg-in"],
                                "outboundTag": "tg-out"
                        }
                        ,
                        {
                                "type": "field",
                                "domain": [
                                        "domain:epochtimes.com",
                                        "domain:epochtimes.com.tw",
                                        "domain:epochtimes.fr",
                                        "domain:epochtimes.de",
                                        "domain:epochtimes.jp",
                                        "domain:epochtimes.ru",
                                        "domain:epochtimes.co.il",
                                        "domain:epochtimes.co.kr",
                                        "domain:epochtimes-romania.com",
                                        "domain:erabaru.net",
                                        "domain:lagranepoca.com",
                                        "domain:theepochtimes.com",
                                        "domain:ntdtv.com",
                                        "domain:ntd.tv",
                                        "domain:ntdtv-dc.com",
                                        "domain:ntdtv.com.tw",
                                        "domain:minghui.org",
                                        "domain:renminbao.com",
                                        "domain:dafahao.com",
                                        "domain:dongtaiwang.com",
                                        "domain:falundafa.org",
                                        "domain:wujieliulan.com",
                                        "domain:ninecommentaries.com",
                                        "domain:shenyun.com"
                                ],
                                "outboundTag": "blocked"
                        }                       ,
                {
                    "type": "field",
                    "protocol": [
                        "bittorrent"
                    ],
                    "outboundTag": "blocked"
                }
                        //include_ban_ad
                        //include_rules
                        //
                ]
        },
        "transport": {
                "kcpSettings": {
            "uplinkCapacity": 100,
            "downlinkCapacity": 100,
            "congestion": true
        }
        }
}
