---
title: "MACabre: darle a la capa 2 el cariño que merece"
date: 2026-11-02
tags: ["redes", "seguridad", "capa2", "mikrotik", "open-source"]
draft: false
---

Dedicamos años a fortificar la capa 3. Filtramos prefijos, firmamos
rutas, discutimos sobre RPKI mientras se enfría el café. Y entonces
alguien entra en una sala de reuniones, enchufa un portátil y el
switch le entrega encantado las llaves del reino. La capa 2 es ese
suelo que nadie mira hasta que tropieza con él.

Así que me puse a construir **MACabre**.

## ¿Y esto qué es?

MACabre (sí, *MAC* + *macabre*, y no me arrepiento) es una suite de
auditoría de capa 2 de código abierto en Python, con interfaz
gráfica de escritorio en PySide6 y Scapy haciendo el trabajo sucio
por debajo. La apuntas a tu propio laboratorio, eliges un ataque en
el menú y observas cómo aguantan tus switches, bridges y puertos de
acceso.

Si alguna vez has usado
[Yersinia](https://github.com/tomac/yersinia), te sentirás como en
casa: es la inspiración de todo esto. Pero MACabre no es un fork, es
código nuevo sobre una base de Python moderna, así que da gusto
ampliarlo y mantenerlo vivo.

## Dos trabajos, una herramienta

Estoy construyendo MACabre con una doble intención:

- **Auditoría de verdad.** Probar la resiliencia de redes propias o
  que tengo autorización para auditar, ese borde de acceso que casi
  siempre se ignora.
- **Formación.** Esta es la parte que más me ilusiona. Quiero que sea
  un apoyo visual en clase, algo que *enseñar* en lugar de solo
  describir. Cuando imparto los cursos oficiales de MikroTik
  **MTCSE** y **MTCSWE**, una cosa es decir "el DHCP starvation agota
  el pool" y otra muy distinta lanzarlo en directo y luego recorrer
  las funciones de RouterOS que lo frenan.

Porque de eso va todo esto: en mi cabeza, cada ataque de MACabre va
emparejado con su defensa. Entender el ataque es como aprendes a
pararlo.

## La hoja de ruta, a grandes rasgos

Empezando por los clásicos de la capa 2: primero el agotamiento del
pool DHCP, y después LLDP, CDP y STP/BPDU. Junto a la app de
escritorio hay una versión solo de consola que corre como
contenedor, incluso directamente en equipos MikroTik RouterOS, para
probar desde un punto real de la topología y no desde un portátil en
una esquina.

## Pásate a saludar

Vive en GitHub como
[vitokosk8/MACabre](https://github.com/vitokosk8/MACabre), con
licencia Apache 2.0 y una primera vista previa `v0.1.0`. Está en el
día uno: incidencias, ideas y "¿y si…?" son más que bienvenidos.
