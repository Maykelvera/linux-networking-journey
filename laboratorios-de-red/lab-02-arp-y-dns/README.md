```
# Laboratorio 02: Resolución de Direcciones ARP (Capa 2) y DNS Jerárquico (Capa 7)

## 1. Problemática y Objetivos Técnicos

* **Entorno de Trabajo:** Artix Linux (sin systemd), Interfaz wlan0, Host IP 192.168.3.11, Gateway IP 192.168.3.1.
* **Objetivo L2/L3:** Capturar e inspeccionar la resolución de direcciones de hardware (MAC) a partir de direcciones lógicas (IP) mediante la depuración de tramas ARP en la terminal.
* **Objetivo L7:** Analizar la resolución jerárquica e iterativa de nombres de dominio (DNS) desde la raíz (.) hasta el servidor autoritativo.

## 2. Ejecución Práctica y Salidas de Terminal

### 2.1 Identificación del Gateway y Limpieza de Caché

```bash
# Inspección de la tabla de enrutamiento
ip route show

# Limpieza de la tabla de vecinos en la memoria RAM del kernel
sudo ip neighbor flush dev wlan0

```

### 2.2 Captura de Tramas ARP en Vivo (tcpdump)

```
17:49:52.795882 ARP, Ethernet (len 6), IPv4 (len 4), Request who-has 192.168.3.1 tell 192.168.3.11, length 28
17:49:52.797935 ARP, Ethernet (len 6), IPv4 (len 4), Reply 192.168.3.1 is-at 78:04:e3:b9:e4:9b, length 28

```

### 2.3 Verificación de la Tabla ARP en Kernel

```
ip neighbor show dev wlan0

```

### 2.4 Traza Jerárquica DNS (dig +trace)

```
dig +trace google.com
```