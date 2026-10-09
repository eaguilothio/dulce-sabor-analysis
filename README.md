# DulceSabor Pastelería — Rentabilidad por canal de venta

Proyecto de análisis de datos con **Power Query y Excel** sobre una pastelería ficticia (datos simulados de 2024).

**¿Qué canal de venta gana dinero de verdad?**

**Resumen:** el canal que más vende es el que menos margen deja. Los **marketplaces** (Glovo y Uber Eats) concentran el **55,3 % de la facturación**, pero su margen es del **23,0 %** frente al **46,2 %** de la web y el **51,6 %** de la recogida en obrador. La causa no es el producto: marketplace pesa un 55,3 % en los costes de producto, igual que en la venta, pero concentra el **91,6 % de la comisión**.

---

## Pregunta de negocio

**¿Qué canales aportan realmente rentabilidad al negocio una vez descontados costes y comisiones?**

Para responder a esta pregunta, el análisis sigue estas cuestiones:

* ¿Cómo se reparte la venta entre canales?
* ¿Qué canales dejan más margen?
* ¿Qué canal deja poco margen y por qué?
* ¿Qué acciones se pueden proponer?

---

## Cómo se calcula la rentabilidad

El análisis parte de la tabla combinada (1.673 líneas de pedido) y sigue la cadena:

* **Facturación** = unidades × precio.
* **Costes** = unidades × coste de producto (ingredientes + packaging).
* **Comisión del canal** = facturación × % de comisión del canal.
* **Margen bruto** = facturación − costes − comisión.
* **Margen %** = margen bruto / facturación.

Cada importe se acompaña de su **peso en el total** (% facturación, % costes y % comisión), calculado con una tabla dinámica por tipo de canal.

---

## ¿Cómo se reparte la venta entre canales?

Los canales se agrupan en tres tipos:

* **Directo local:** recogida en obrador.
* **Directo web:** web propia y app propia.
* **Marketplace:** Glovo y Uber Eats.

| Tipo de canal | Facturación | % facturación | Costes | % costes | Comisión | % comisión | Margen bruto | Margen % |
|---|---|---|---|---|---|---|---|---|
| Directo local | 16.076,80 € | 20,1 % | 7.783,60 € | 20,3 % | 0,00 € | 0,0 % | 8.293,20 € | 51,6 % |
| Directo web | 19.597,60 € | 24,5 % | 9.376,10 € | 24,4 % | 1.175,86 € | 8,4 % | 9.045,64 € | 46,2 % |
| Marketplace | 44.215,30 € | 55,3 % | 21.192,60 € | 55,3 % | 12.865,17 € | 91,6 % | 10.157,53 € | 23,0 % |
| **Total** | **79.889,70 €** | **100 %** | **38.352,30 €** | **100 %** | **14.041,03 €** | **100 %** | **27.496,37 €** | **34,4 %** |

Más de la mitad de la venta depende de plataformas externas.

---

## ¿Qué canales dejan más margen?

* **En euros**, el que más margen aporta es **marketplace** (10.157,53 €), pero por volumen.
* **En porcentaje**, el mejor es el **directo local** (51,6 %), seguido de la web (46,2 %).

---

## ¿Qué canal deja poco margen y por qué?

**Marketplace** deja solo un **23,0 %** de margen, más de 11 puntos por debajo del total del negocio (34,4 %).

La diferencia no viene del coste de producto, que pesa lo mismo que la venta (55,3 %). Viene de la **comisión**: marketplace paga **12.865,17 €**, frente a **1.175,86 €** de la web y **0 €** del local. Es decir, un **29,1 %** de su facturación, frente al 6,0 % en la web.

---

## Conclusiones

El análisis muestra que:

* Marketplace genera el **55,3 %** de la facturación, pero su margen es del **23,0 %**, frente al **34,4 %** del total.
* Los canales directos dejan un margen del **46-52 %**.
* Los costes de producto se reparten igual que la venta, así que no explican la diferencia.
* Marketplace concentra el **91,6 %** de la comisión: el coste de vender por ese canal es lo que reduce su rentabilidad.

---

## Acciones propuestas

**1. Impulsar la web y la app propias frente a los marketplaces**

Incentivar el pedido directo con acciones como **envío gratuito a partir de un determinado importe** o **promociones exclusivas en la web**, con el objetivo de que una parte de los clientes de marketplace compre en canales propios.

**2. Revisar las condiciones de los marketplaces**

Valorar la **renegociación de comisiones** o ajustar los **precios en marketplace** para compensar el coste de la comisión.

**3. Hacer seguimiento del margen por canal**

Revisar periódicamente el **margen % de cada canal** para comprobar si el cambio de reparto de ventas se refleja en el margen total.

**Próximos pasos:** estudiar la estacionalidad (pico de diciembre), las incidencias por canal y el margen por producto en cada canal.

---

## Herramientas

* Power Query (limpieza y combinación)
* Excel (tabla dinámica y fórmulas)

---

## Archivos del repositorio

```text
0_DulceSabor_Pasteleria_Datos_Crudos.xlsx          → datos originales
1_DulceSabor_Pasteleria_Datos_Limpios.xlsx         → datos tras la limpieza
2_DulceSabor_Pasteleria_Datos_Combinados.xlsx      → tabla combinada y enriquecida
3_DulceSabor_Pasteleria_Analisis_Rentabilidad.xlsx → hoja de análisis con la tabla dinámica
archivos_proceso/                                  → documentos del proceso 
README.md                                          → presentación del proyecto
```

> Datos simulados con fines formativos: las conclusiones no son extrapolables a un negocio real.
