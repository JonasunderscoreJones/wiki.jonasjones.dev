# Performance
---
McWebserver attempts to be as lightweight as possible.

An experiment shows that this is clearly the case. Even when the server is getting DDOS'd and the website might not be available due to the high demand of the DDOS, the server still runs perfectly fine.

The following gif shows a DDOS script using 300 threads (300 simultaneous requests at the same time) and the server's MSPT (Milliseconds per Tick) only rises by about 2ms while under the DDOS attack.

Notice: This isn't a scientific test and I wouldn't claim that the server can withstand a real DDOS attack. The results only give an idea of the performance impact under elevated load and medium demand.

[View performance impact (gif)](https://cdn.jonasjones.dev/misc/mcwebserver-ddos-performance-impact.gif)