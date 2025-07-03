## Ejercicio 1:
$$V\frac{dC}{dt}= QC_{in}-Q_oC$$
En estado estacionario: 
$$0= F_{in}-Q_oC$$
El flujo de salida es el siguiente: 
$$Q_0 = 15400\frac{m}{y}\cdot1210m\cdot10^5m = 1.8634\cdot10^7\frac{m^3}{y}$$
$$C = \frac{F_{in}}{Q_o}=\frac{1375\cdot10^6}{1.8634\cdot10^7}\frac{lb\cdot}{m^3}=73.7898\cdot10^{-3}\frac{lb}{m^3}$$

## Ejercicio 2:
$$Q=0.8m^3/s;\quad V = 3600 m^3$$
$$C_{b_0}=10^4\frac{\mathrm{bacterias}}{l};\quad C_{c_0}=1000\frac{mg}{l}$$
$$C_c = 2 \frac{mg}{l}$$
Las ecuaciones que describen al sistema son las siguientes: 


Calculando el flujo de cloro requerido:

$$Q_{C_i}C_{c_o}=(Q+Q_{C_i})C_C$$
$$Q_{C_i}(C_{c_o}-C_C) = QC_C$$
$$Q_{C_i} = \frac{QC_C}{C_{c_o}-C_C}$$
$$Q_{C_i} = \frac{0.8\frac{m^3mg}{l\cdot s}}{1000\frac{mg}{l}-2\frac{mg}{l}}=8.016\cdot10^{-4}\frac{m^3}{s}$$
Obteniendo las bacterias, asumiendo que se comporta como un reactor CMFR:
$$r_b = k'C_b= \frac{0.05C_c}{1+C_c}C_b\frac{\mathrm{bacterias}}{l\cdot s}= \frac{0.05\cdot2}{1+2}\frac{1}{s}\cdot C_b$$
$$k'=\frac{1}{30s}$$
$$C_{b_{out}}=\frac{Q\cdot C_{b_0}}{Q_o+k'V}$$
$$C_{b_{out}}=\frac{0.8\cdot 10000\frac{\mathrm{bacteria}\cdot m^3}{l\cdot s}}{0.8008\frac{m^3}{s}+\frac{3600}{30}\frac{m^3}{s}} \approx 66.2247\frac{\mathrm{bacterias}}{l}$$

