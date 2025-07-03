# Sistema dinámico
Un sistema dinámico es un [[modelo]] de la realidad que lo describe por medio de la siguiente ecuación diferencial:

$$\frac{d}{dt}\mathbf{x} = f(\mathbf{x},t,\mathrm{u};\beta)$$

Donde $\mathbf{x}$ es el vector de estados, $t$ es el tiempo, $\mathrm{u}$ son las entradas o variables controlables del [[Sistema|sistema]], y $\beta$ son los [[Parámetros]] que lo describen.

Esta vista es meramente geométrica y está muy basada en la intuición de Henri Poincaré

## Vista alternativa
Alternativamente, un sistema dinámico puede describirse como un campo $(\mathcal{M},n,\mathbf{F})$, donde:

- $n\in\mathbb{Z}$ es el tiempo discreto, 
- $\mathcal{M}\subset\mathbb{R}^N$ es el [[Espacio estado|espacio estado]] $N$-dimensional que contiene a la serie de tiempo $\{\mathbf{x}_n\}$, y 
- $\mathbf{x}_i \mapsto \mathbf{F}(\mathbf{x}_i)=\mathbf{x}_{i+1}$ es la ley de evolución del sistema dinámico.  

Alternativamente, si se considera un tiempo continuo, el sistema dinámico $(\mathcal{M},t,\mathbf{F}^t)$ tiene a $t$ como el tiempo continuo, y el mapeo $\mathbf{F}^t$ evoluciona conforme $\mathbf{x}_0\longmapsto\mathbf{F}^t(\mathbf{x}_0)=\mathbf{x}_t$. Se relacionan uno con el otro porque es normal hacer mediciones a periodos de tiempo discretos ($\Delta t$), alternativamente $\mathbf{F}^{\Delta t}(\mathbf{x}_t)=\mathbf{x}_{t+\Delta t}$.