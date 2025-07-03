Este es un [[Modelo|modelo]] de [[Convección|convección]] y [[Conducción|conducción de calor]]:
$$\frac{dT}{dt} = -\frac{1}{\tau}\left(T_i-\frac{R_{conv}T_i+R_{cond}T_{amb}}{R_{conv}+R_{cond}}\right)$$
$$\frac{dT}{dt} = -\frac{1}{\tau}\left(T_i\left(1-\frac{R_{conv}}{R_{conv}+R_{cond}}\right)-\frac{R_{cond}T_{amb}}{R_{conv}+R_{cond}}\right)$$
$$\frac{1}{\left(T_i\left(1-\frac{R_{conv}}{R_{conv}+R_{cond}}\right)-\frac{R_{cond}T_{amb}}{R_{conv}+R_{cond}}\right)}\frac{dT}{dt} = -\frac{1}{\tau}$$
Sea $\alpha = 1-\frac{R_{conv}}{R_{conv}+R_{cond}}$ y $\beta = \frac{R_{cond}T_{amb}}{R_{conv}+R_{cond}}$:
$$\frac{1}{\alpha T - \beta}\frac{dT}{dt} = -\frac{1}{\tau}$$
$$\int_{T_0}^T\frac{dT}{\alpha T-\beta} =-\frac{1}{\tau} \int_0^tdt$$
$$\frac{1}{\alpha}\ln\left(\frac{\alpha T-\beta}{\alpha T_0-\beta}\right) = -\frac{t}{\tau}$$
$$\frac{\alpha T-\beta}{\alpha T_0-\beta} =\exp\left( -\frac{\alpha t}{\tau}\right)$$
$$ T =\frac{\beta}{\alpha}+\left(T_0-\frac{\beta}{\alpha}\right)\exp\left(-\frac{\alpha t}{\tau}\right)$$
