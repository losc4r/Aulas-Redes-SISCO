!Criação dos Gateway (sw 3650)
!enable
    configure terminal
        ip routing (serve para o sw fazer roteamento na rede)
        interface vlan 20 (servidores topologia)
            description Interface de Gateway da VLAN 20
            ip address 192.168.20.254 255.255.255.0
            no shutdown
            end 
write 
show running-config
show ip interface brief
show ip route 
ping 192.168.20.254 (pingando gateway dos servidores)
ping 192.168.20.1 (pingando servidor 1)

========================================================

!Criação dos Gateway (sw 3650)
!enable
    configure terminal
        interface vlan 30 (acess point topologia)
            description Interface de Gateway da VLAN 30
            ip addres 192.168.30.254 255.255.255.0
            ip helper-address 192.168.20.2 (ip do servidor 2 vai criar ip's automaticamente para quem se conectar no access point (vlan 30))
            no shutdown
            end
write
show running-config
show ip interface brief
show ip route 
