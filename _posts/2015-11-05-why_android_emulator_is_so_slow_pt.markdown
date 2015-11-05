---
layout: post
title:  "Por que o emulador Android é tão lento? Emuladores vs Simuladores."
date:   2015-11-05 17:00:00 -0200
categories: jekyll update
---

Para desenvolver uma aplicação Android você precisa de um aparelho Android ou usar o emulador. O uso de aparelho reais é mais indicado, quando possível além de ser mais rápido eles fornecem uma sensação real de usar o aplicativo. Infelizmente nem sempre é possível fazer todos os testes usando aparelhos reais, na verdade inevitavelmente o uso de emuladores se torna necessário. Seja para testar uma versão específica do sistema operacional, dimensões específicas do aparelho ou até mesmo para executar testes de integração em cloud.  
Ontem eu expliquei [como enviar SMS para o emulador](https://guitcastro.github.io/jekyll/update/2015/11/04/send_sms_android_emulator_pt.html), continuando minha séries posts sobre emuladores hoje eu vou explicar a diferença entre simuladores e emuladores e porque o emulador do Android é tão lento. 

Primeiramente é preciso entender porque o emulador é lento, quem já desenvolveu aplicativos para iOS sabe que elas são executadas com velocidade semelhante a de um aparelho real. Isso se dá porque o iOS usa um **simulador** e não um **emulador**.

Emuladores levam em conta detalhes internos da arquitetura e do hardware. Ou seja um emulador Android ARM executa instruções da mesma maneira que elas seriam executadas em um hardware com processador ARM, mesmo que a máquina em que o código está sendo executado seja um processador x86. Esse processo de imitar as instruções pode ser muito demorado, pois apesar de algumas instruções serem similares, para fornecer uma emulação apurada é preciso também replicar elementos como tempo de acesso memória, clocking, interrupções e vários outros.   
Emuladores tendem a fornecer uma experiência mais fiel do hardware em custo de performance. [Para emular um Super Nintento perfeitamente](http://www.tested.com/tech/gaming/2712-why-perfect-hardware-snes-emulation-requires-a-3ghz-cpu/) é necessário um CPU de 3Ghz, isto é 140 vezes mais rápido que o CPU do hardware original.

Por outro lado os simuladores só tentam fornecer uma experiência parecida em termos de software, sem se preocupar com detalhes da arquitetura interna do sistema. Desse modo eles tem acesso direto a elementos da máquina hospedeira como acesso a disco, memória e a velocidade da CPU. Por isso simuladores são muito mais rápido, mas isso também gera alguns empecilhos.   
Por não ser a mesma arquitetura o códigos executados no simulador do iPhone não são os mesmo códigos que rodam no aparelho, desse modo você precisa compilar sua aplicação duas vezes. Se você estiver usando uma biblioteca é preciso ter certeza que ela possui compilação para arquitetura x86 e ARM para funcionar no simulador e emulador (felizmente isso é verdade para maioria delas).  
Simuladores fornecem uma experiência menos apurada para o usuário, por exemplo o simulador iOS é *case sensitive* enquanto o aparelho não. Isto pode gerar bugs como por exemplo, ao tentar exibir uma imagem em que o nome do arquivo é em letras minúsculas, usando uma string que contém letras maiúsculas. A imagem vai funcionar corretamente no aparelho real, porém no simulador ela não vai ser carregada.

Espero que vocês tenham entendido a diferença entre emuladores e simuladores e as vantagens e desvantagens de cada um deles. Nos meus próximos posts eu vou fornecer dicas para deixar o emuladore mais rápido.

#Referências

http://stackoverflow.com/questions/1584617/simulator-or-emulator-what-is-the-difference  
http://stackoverflow.com/questions/4544588/difference-between-iphone-simulator-and-android-emulator
http://superuser.com/questions/697322/why-cpu-emulation-is-slow