# service IP 가져오기
```go
package main

import "net"

func serviceIP() (string, error) {
	ip := "127.0.0.1"
	ifaces, err := net.Interfaces() // 네트워크 인터페이스의 목록을 반환한다.
	if err != nil {
		return ip, err
	}
	//https://golang.org/src/net/interface.go?s=2954:2992#L89
	for _, iface := range ifaces {
		if iface.Flags&net.FlagUp == 0 {
			continue //interface down
		}
		if iface.Flags&net.FlagLoopback != 0 {
			continue // loopback interface
		}
		addrs, err := iface.Addrs()
		if err != nil {
			return ip, err
		}
		for _, addr := range addrs {
			var ip net.IP
			switch v := addr.(type) {
			case *net.IPNet:
				ip = v.IP
			case *net.IPAddr:
				ip = v.IP
			}
			if ip == nil || ip.IsLoopback() {
				continue
			}
			ip = ip.To4()
			if ip == nil {
				continue // not an ipv4 address
			}
			return ip.String(), nil
		}
	}
	return ip, nil
}
```
