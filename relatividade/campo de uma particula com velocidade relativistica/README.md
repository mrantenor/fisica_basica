# Campo de Uma Partícula Carregada com Velocidade Relativistica
## Problema
Plot the magnitude of the eletric field of a high-speed cherged particle as a function of the angle $\theta$ made with the direction of motion of the charge, for a given distance r. $$\boldsymbol{E}=\frac{q(1-\beta^2)}{4 \pi \epsilon_0 r^2(1-\beta^2 \sin ^2 \theta)^{3/2}} \frac{\boldsymbol{r}}{r}$$
Assume $\beta = v/c = 0.95$ and take $0 \leq \theta \leq 90 ^\circ$. 

## Demonstração

---

## Gráfico

### Bibliotecas
Para plotarmos o gráfico, precisamos do auxílio das bibliotecas _Numpy_ e _Matplotlib_.
```
import numpy as np
import matplotlib.pyplot as plt
```

### Definição de Variáveis
Vamos definir constantes e variáveis que são necessárias para a equação. A primeira respresentada pela letra ```q``` que é o valor da carga elétrica elementar com valor de $1,6 \cdot 10^{-19} C$ (Coulombs), o ```beta``` que é fornecido pelo enunciado, representando $v/c = 0.95$, ```epsilon``` como a constante de permissividade do vácuo de $\epsilon _0 = 8,85 \cdot 10^{-12}$, o raio definido como ```r``` unitário e ```theta``` variando de $0 \leq \theta \leq 2 \pi$. 

OBS.: O enunciado solicita que a variação do ângulo seja entre $0 \leq \theta \leq \pi /2$, no entanto para realizarmos análises adicionais, aumentaremos o range de variação para até $2\pi$.

```
q = 1.6e-19 
beta = 0.95 
epsilon = 8.85e-12
r = 1 
theta = np.linspace(0,2*np.pi,500)
```

### Definição da Equação
Já temos os dados necessários para definir a equação do campo de uma carga puntiforme com velocidade relativistica:
```
E = (q*(1-(beta**2)))/(4*np.pi*epsilon*(r**2)*((1-(beta**2)*(np.sin(theta)**2))**1.5))
```

### Plotagem do Gráfico

#### Coordenadas Quadráticas
```
ax = plt.axes()
ax.plot(theta,E*1e9)
ax.set_ylabel(r'Campo Elétrico E [10$^{9}$]')
ax.set_xlabel(r'Angulo $\theta$')
ax.set_title('Campo de uma Carga Puntiforme com\n Velocidade Relativistica', size=15)
ax.set_xlim(0,np.pi/2)
plt.show()
```

![Figura 1|480](../../images/campo_relativistico_(1).png)

---
#### Coordenadas Polares
```
ax = plt.axes(projection='polar')
ax.plot(theta,E*1e9)
ax.set_xlabel(r'Angulo $\theta$')
ax.set_title('Campo de uma Carga Puntiforme com\n Velocidade Relativistica (Coord. Polares)')
plt.show()
```


![Figura 2|400](../../images/campo_relativistico_(2).png)
