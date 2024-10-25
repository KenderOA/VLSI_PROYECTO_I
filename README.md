# VLSI_PROYECTO_I

## Parte 1. Determinación de las resistencias de canal de transistores mínimos NMOS y PMOS para el proceso XH018

### Parte 1.a. Determinación de las resistencias de canal de transistores mínimos NMOS y PMOS para el proceso XH018

**Fórmula de la resistencia cuando el transistor está en saturación**

$$R=\frac{V_{DD}}{2\cdot I_{sat}} \quad(1)$$

**Fórmula de la resistencia cuando el transistor está en transición**

$$R_{eff}=\frac{V_{DD}}{I_H+I_L} \quad(2)$$

Los valores utilizados para los cálculos provienen de los parámetros de transistores de 1.8V (ne, pe) de un proceso XT018 de 0.18 $\mu$ m. En estos cálculos, se desprecia $I_L$​ debido a que su valor es muy pequeño en comparación con otras corrientes en el circuito. Además, es importante señalar que para obtener las resistencias en ohmios, se multiplicaron las ecuaciones (1) y (2) por el ancho de los transistores.

**Para el transistor NMOS**
Para la ecuación (1)

$$R_N=\frac{1.8V}{2 \cdot 475 \times 10^{-6}\frac{A}{\mu m} \cdot0.36 \mu m} \approx 5.2k \Omega$$

Para la ecuación (2)

$$R_{eff_N}=\frac{1.8V}{475 \times 10^{-6}\frac{A}{\mu m} \cdot0.36 \mu m} \approx 10.5 k\Omega$$

**Para el transistor PMOS**

Para la ecuación (1)

$$R_P =\frac{1.8V}{2 \cdot 170 \times 10^{-6}\frac{A}{\mu m} \cdot0.72 \mu m} \approx 7.3k\Omega$$

Para la ecuación (2)

$$R_{eff_P}=\frac{1.8V}{170 \times 10^{-6}\frac{A}{\mu m} \cdot0.72 \mu m} \approx 14.7 k\Omega$$

### Parte 1.b. Determinación de las capacitancias equivalentes que tiene el transistor de tamaño mínimo y constante RC para el proceso

Los valores para los siguientes cálculos se tomaron de los parámetros para transistores 1.8V (ne,pe) de un proceso XH018 - 18 $\mu$m.

**Fórmula de la capacitancia parásita si se considera pesimista**

$$C = W_{dib}L_{dib}C_{ox}+W_{dib}C_{ov} \quad(3)$$

**Fórmula de la constante RC ($\tau$) para NMOS**

$$\tau= 3R_{eff_N}C \quad(4)$$
**Fórmula de la constante RC ($\tau$) para PMOS**
$$\tau= \frac{3}{2}R_{eff_P}C \quad(5)$$


### Transistor NMOS

**Cálculo de la capacitancia**

Para determinar el valor de $C$ para el transistor NMOS se utilizó la ecuación (3).

$$C = 0.36 \mu m \cdot 0.18 \mu m \cdot 8.46 \tfrac{fF}{\mu m^2} + 0.36 \mu m \cdot 0.33 \tfrac{fF}{\mu m} \approx 0.67 fF$$

**Cálculo de la constante RC ($\tau$)**

Para determinar el valor de la constante **RC** para el transistor NMOS se utilizó la ecuación (X).

$$\tau = 3 \cdot 10.5k \Omega \cdot 0.67 fF \approx  21.1 ps$$

### Transistor PMOS

**Cálculo de la capacitancia**

Para determinar el valor de $C$ para el transistor NMOS se utilizó la ecuación (3).

$$C = 0.72 \mu m \cdot 0.18 \mu m \cdot 8.91 \tfrac{fF}{\mu m^2} + 0.72 \mu m \cdot 0.32 \tfrac{fF}{\mu m} \approx 1.39 fF$$

**Cálculo de la constante RC ($\tau$)**

Para determinar el valor de la constante **RC** para el transistor NMOS se utilizó la ecuación (X).

$$\tau = \frac{3}{2} \cdot 14.7k\Omega \cdot 1.39 fF \approx  30.64 ps$$

## Parte 2. Diseño de un inversor mínimo de tamaño óptimo

### Parte 2.a. Inversor y NMOS mínimo permitido
Para esta sección se diseña a nivel de esquematico, el NMOS de tamaño mínimo permitido por las reglas con un lambda de 90 nm, la relación dentro del transistor mínimo 4:2 lambda resulta en un ancho de NMOS de 360 nm y un largo de 180 nm. Además, se establece de manera empírica la relación PMOS/NMOS cumpliendo un margen de ruido simétrico (punto de umbral o transición en VDD/2).
![image](https://github.com/user-attachments/assets/3fb6f324-145c-4f9f-b6eb-1e99cec64ab5)

Para ello se obtuvo la función de fransferencia del inversor, donde se estima de maneara manual que el inversor debe tener PMOS 5 veces más area que el NMOS para que los parámetros Beta tengan una relación Bp/Bn = 1.
![image](https://github.com/user-attachments/assets/5a73812d-9a12-4e1a-8550-cc566db7d545)


