# Atividade Azure - Comunicação entre Máquinas Virtuais

## Objetivo

Configurar duas máquinas virtuais no Microsoft Azure e estabelecer comunicação entre elas por meio de uma rede virtual privada.

## Ambiente

Foram utilizadas duas máquinas virtuais Windows na região **Mexico Central**:

- `teste` - IP privado: `172.16.0.6`
- `teste2` - IP privado: `172.16.1.4`

As duas máquinas foram configuradas na mesma:

- VNet: `vnet-mexicocentral-1`
- Sub-rede1: `snet-mexicocentral-1`
- Sub-rede2: `snet-mexicocentral-2`

## Configuração de Rede

As máquinas foram criadas utilizando a mesma VNet e sub-rede diferentes.

Também foi configurada uma regra no Firewall do Windows para permitir tráfego ICMP:

```powershell
New-NetFirewallRule -DisplayName "Allow ICMPv4-In" -Protocol ICMPv4 -IcmpType 8 -Direction Inbound -Action Allow
