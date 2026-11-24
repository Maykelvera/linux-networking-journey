# Laboratorio 01: Diagnóstico Base de Red en Artix Linux

## Objetivo
Inspeccionar las interfaces de red activas, identificar la puerta de enlace predeterminada y medir la latencia local e internacional mediante herramientas nativas de Linux.

## Datos de mi entorno
- **Interfaz de red activa:** wlan0
- **IP Privada de mi equipo:** 192.168.3.11
- **Puerta de enlace (Router):** 192.168.3.1

## Comandos ejecutados y su propósito
- `ip address`: Listó las interfaces de red y sus direcciones IP asignadas.
- `ip route`: Reveló la tabla de enrutamiento y el Gateway predeterminado.
- `ping -c 5`: Verificó la conectividad y midió la pérdida de paquetes (0% packet loss) y la latencia en milisegundos.
