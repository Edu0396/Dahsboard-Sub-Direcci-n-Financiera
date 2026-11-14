# Ejecución de Cartera de Créditos por IFI

Tablero interactivo para dar seguimiento a la **cartera de créditos colocados por cada Institución Financiera Intermediaria (IFI)** en los programas **CREDIMUJER · Productores individuales · SSE**.

Es una sola página HTML, autocontenida: no necesita servidor, base de datos ni instalación. Se abre en el navegador y lee la base de cartera de la Sub Dirección Financiera de SENPRENDE.

> **Elaborado por:** MSc. Eduardo Quan, MSc. Eduardo Canales
> **Fuente de datos:** Sub Dirección Financiera, SENPRENDE

---

## ¿Qué permite hacer?

- Ver cuánto se ha colocado, cuántos créditos son y cómo avanza cada IFI frente a su **meta a diciembre de 2026**.
- Saber **dónde se coloca**: mapa de Honduras por departamento y detalle por municipio.
- Comparar IFIs, sectores económicos, programas o proyectos y género de las personas beneficiarias.
- Revisar la **colocación mes a mes** en una gráfica lineal.
- Filtrar todo el tablero por programa, IFI, departamento, sector económico, género y mes.
- Actualizar la información cargando una versión nueva de la base en Excel o CSV.

## Páginas

| Página | Contenido |
|---|---|
| **Resumen** | Nueve indicadores clave (monto colocado, colocación global frente a la meta, meta a financiar, créditos colocados, saldo de capital, créditos con atraso, plazo promedio, porcentaje de créditos a mujeres y sector con mayor colocación), avance de la meta por IFI, colocación por mes y por departamento. |
| **Por IFI** | Ficha comparativa de cada institución: monto, número de créditos, plazo, tasa, saldo, departamentos y participación de mujeres. |
| **Departamento** | Mapa de colocación por departamento (con vista de tabla) y cartera por municipio. |
| **Sector económico** | Sector tal como lo reporta cada IFI, en gráfico y en cifras. |
| **Programa y género** | Programas o proyectos, y distribución por género (Femenino y Masculino). |
| **Detalle de créditos** | Un renglón por crédito, con búsqueda, orden y paginación. *Protegida con contraseña.* |
| **Notas de la base** | Revisiones automáticas de calidad de datos y definiciones de cada indicador. *Protegida con contraseña.* |

## Cómo usarlo

1. Descargue `index.html` y ábralo con cualquier navegador moderno (Chrome, Edge, Firefox o Safari).
2. Use el menú de la izquierda para cambiar de página; el botón de tres rayas lo contrae o lo despliega.
3. Use los filtros de la parte superior para acotar la información.
4. Cambie entre tema claro y oscuro con el botón **Tema**.

### Actualizar la base

El botón **Cargar Excel o CSV actualizado** (en el menú) lee el archivo directamente en el navegador; los datos no se envían a ningún servidor.

- **Excel (.xlsx):** el tablero busca la hoja `BD_Cartera`. Si el archivo trae una hoja `Catalogos`, también la usa para los sectores económicos.
- **CSV:** debe tener los mismos encabezados que la hoja `BD_Cartera`.
- **Columnas obligatorias:** `Institucion_IFI`, `Monto_Original_Credito` y `Fecha_Desembolso`.
- **Columnas que usa si existen:** número de préstamo, tipo de persona, género, departamento, municipio, plazo en meses, tasa de interés corriente, proyecto, sub producto, sector económico, estado del crédito, días de atraso, saldo de capital, saldo de capital vencido y fecha de corte.

Para leer archivos `.xlsx` el tablero descarga el lector de Excel (SheetJS) desde Internet. Si la red lo bloquea, guarde la hoja como CSV y cárguela de nuevo.

## Criterios de cálculo

- **Monto colocado:** suma del monto original de los créditos que cumplen los filtros.
- **Colocación global y avance por IFI:** monto colocado entre la meta correspondiente.
- **Créditos a mujeres:** porcentaje de créditos otorgados a mujeres sobre los créditos que tienen género. Los créditos a CRAC y asociaciones no tienen género: cuentan en los totales, pero no aparecen en los cuadros por género.
- **Créditos con atraso:** créditos con días de atraso mayores que 0 o con saldo de capital vencido.
- **Sector con mayor colocación:** sector con más monto colocado y su porcentaje del total; si hay empate se muestran todos los sectores empatados.

## Privacidad y publicación

- El tablero **no muestra nombres ni números de identidad** de las personas beneficiarias.
- Los datos de la cartera viajan **dentro del propio archivo HTML**. Quien tenga el archivo, o acceso al repositorio, puede ver esa información.
- La contraseña de las páginas *Detalle de créditos* y *Notas de la base* es solo un bloqueo de pantalla; **no es una medida de seguridad** y no cifra los datos.
- Por eso, si el repositorio es público, publique una versión **sin datos reales** (por ejemplo, con datos de ejemplo) o mantenga el repositorio **privado**.

## Tecnología

- HTML, CSS y JavaScript sin dependencias de compilación, en un solo archivo.
- Gráficos, mapa de Honduras e íconos dibujados en SVG y CSS, incluidos en el archivo.
- Tipografías: **Anton** (títulos y menú, desde Google Fonts) y **Tahoma** (resto del tablero; si el equipo no la tiene, se usa Verdana u otra similar).
- Lector de Excel opcional: [SheetJS](https://sheetjs.com/) 0.18.5, solo al cargar archivos `.xlsx`.

## Créditos y licencias de terceros

- Íconos: biblioteca *Iconos_Financiamiento_SENPRENDE*, con pictogramas basados en [Font Awesome Free](https://fontawesome.com/license/free) © Fonticons, Inc. (licencia CC BY 4.0), adaptados en color para SENPRENDE.
- Logotipo y escudo: propiedad de SENPRENDE; su uso está sujeto a las normas institucionales.
