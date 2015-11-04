---
layout: post
title:  "Como enviar SMS para o emulador Android"
date:   2015-11-04 20:11:18 -0200
categories: jekyll update
---

Esse eu meio primeiro post e eu vou mostrar uma solução simples para enviar
SMS para o emulador Android.

Para enviar SMS você precisa apenas:

* Abrir console/terminal
* Descobrir o número da porta, no título emulador 
* Conectar ao emulador usando telnet : `telnet localhost [portnumber]`
* Enviar a sms digitanto: `sms send senderPhoneNumber textmessage`

[Reference](http://stackoverflow.com/a/4325836/1107651)
