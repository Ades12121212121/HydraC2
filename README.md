# HydraC2 - Advanced DoS Command & Control Tool

HydraC2 es una herramienta avanzada de Command & Control (C2) para ataques DoS, escrita en Go, con un enfoque en flexibilidad, eficiencia y capacidades avanzadas de bypass para firewalls y protecciones.

## Características

- **Múltiples métodos de ataque**: TCP, UDP, HTTP, SYN y Minecraft
- **Modo Bypass**: Detección automática de protecciones y adaptación de estrategias
- **Estadísticas en tiempo real**: Seguimiento de paquetes y bytes enviados
- **Interfaz CLI intuitiva**: Con ayuda, colores y ejemplos de uso
- **Resolución de dominios**: Conversión automática de dominios a IPs
- **Ataques específicos para protocolos**: Payloads adaptados a cada servicio (HTTP, DNS, NTP, SMTP, etc.)
- **Técnicas avanzadas de evasión**: Fragmentación de paquetes, timing aleatorio y fingerprinting
- **Impenetrable**: Diseñado para superar incluso las protecciones más avanzadas
- **Sistema de opciones avanzadas**: Flags activables para personalizar cada ataque
- **Ataques Minecraft avanzados**: Detección y explotación de plugins, handshake flood, login flood, tab complete, chunk requests y más

## Comandos disponibles

- `help` - Muestra la ayuda y comandos disponibles
- `methods` - Muestra los métodos de ataque disponibles
- `advanced` - Muestra las opciones avanzadas disponibles
- `stats` - Muestra estadísticas del ataque actual
- `resolve <dominio>` - Resuelve un dominio a IP
- `tcp <ip> <puerto> <threads> <tiempo> [opciones]` - Inicia un ataque TCP
- `udp <ip> <puerto> <threads> <tiempo> [opciones]` - Inicia un ataque UDP
- `http-flood <url> <método> <threads> <tiempo> [opciones]` - Inicia un ataque HTTP Flood
- `syn-flood <ip> <puerto> <threads> <tiempo> [opciones]` - Inicia un ataque SYN Flood
- `minecraft <ip> <puerto> <threads> <tiempo> [opciones]` - Inicia un ataque especializado para servidores Minecraft
- `clear` - Limpia la pantalla
- `exit/quit` - Salir de HydraC2

## Opciones avanzadas

HydraC2 permite personalizar cada ataque con opciones avanzadas que se pueden combinar libremente:

- **bypass** - Activa modo bypass para evadir protecciones (genera payloads específicos para cada protocolo)
- **stealth** - Reduce la huella del ataque (más lento pero más difícil de detectar)
- **rotate** - Rota IPs/User-Agents para evadir bloqueos
- **encrypt** - Encripta el tráfico para evadir inspección profunda de paquetes (DPI)
- **emulate** - Emula tráfico de clientes legítimos con cabeceras y comportamientos realistas
- **distributed=IP** - Conecta a un coordinador para ataque distribuido

### Ejemplos de uso con opciones avanzadas

```bash
# Ataque HTTP con bypass y rotación de User-Agents
http-flood https://ejemplo.com GET 100 60 bypass rotate

# Ataque UDP con emulación de tráfico legítimo y modo sigiloso
udp 192.168.1.1 80 50 120 emulate stealth

# Ataque a servidor Minecraft con bypass y encriptación
minecraft mc.servidor.com 25565 200 300 bypass encrypt

# Ataque SYN con todas las opciones activadas
syn-flood 10.0.0.1 443 150 600 bypass stealth rotate encrypt emulate
```

## Ataques Minecraft avanzados

HydraC2 incluye capacidades especiales para servidores Minecraft:

- **Detección automática de plugins**: Identifica plugins vulnerables
- **Handshake flood**: Sobrecarga el proceso de handshake
- **Login flood**: Inunda con intentos de login
- **Tab complete**: Explota la función de autocompletado
- **Chunk requests**: Solicita chunks extremos para sobrecargar el servidor
- **Plugin exploits**: Explota vulnerabilidades específicas de plugins populares
- **NBT exploits**: Utiliza paquetes NBT malformados
- **World load**: Fuerza la carga de chunks en coordenadas extremas

### Lista de plugins detectables (40+)

HydraC2 puede detectar y explotar más de 40 plugins populares, incluyendo:
- EssentialsX, WorldEdit, WorldGuard, ProtocolLib, Vault
- LuckPerms, CoreProtect, GriefPrevention, PlaceholderAPI
- AuthMe, BungeeCord, Multiverse, ClearLag, CMI
- Y muchos más...
![2025-04-30 19_02_10-Layana - Windsurf - hydrac2 go](https://github.com/user-attachments/assets/61c2e4dd-cfc8-4679-820f-d3725c3385cb)

## Características técnicas

- **Generación de payloads avanzados**: Crea payloads específicos para cada protocolo
- **Evasión de DPI**: Técnicas para evadir inspección profunda de paquetes
- **Emulación de clientes legítimos**: Comportamiento realista para evadir detección
- **Timing aleatorio**: Varía el tiempo entre paquetes para evadir detección basada en patrones
- **Fragmentación de paquetes**: Divide los paquetes para evadir sistemas de detección
- **Rotación de User-Agents**: Más de 50 User-Agents diferentes para HTTP
- **Análisis de servidores Minecraft**: Detección de versión, plugins y vulnerabilidades

## Interfaz de usuario

HydraC2 cuenta con una interfaz de línea de comandos profesional y fácil de usar:
![2025-04-30 19_01_56-Layana - Windsurf - hydrac2 go](https://github.com/user-attachments/assets/8260c977-dffe-4230-9e4e-85e680adcca8)

- **Banner colorido**: Identificación visual clara de la herramienta
- **Comandos intuitivos**: Estructura simple y consistente
- **Ayuda detallada**: Información completa sobre comandos y opciones
- **Barra de progreso**: Visualización en tiempo real del avance del ataque
- **Estadísticas en vivo**: Información actualizada sobre paquetes y bytes enviados
- **Colores para mejor legibilidad**: Diferenciación visual de comandos, opciones y resultados

## Aviso legal

Esta herramienta está diseñada únicamente con fines educativos y de pruebas en entornos controlados. El uso de esta herramienta para atacar objetivos sin autorización explícita es ilegal y puede resultar en consecuencias legales graves. Los autores no se hacen responsables del mal uso de esta herramienta.
