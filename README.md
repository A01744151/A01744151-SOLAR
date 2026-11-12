# A01744151 SOLAR — Plataforma de cotización V3

Sitio web estático para GitHub Pages, sin servidor ni base de datos, con dos páginas:

- `index.html`: catálogo de seis modelos de referencia + modelo personalizado, cálculo de consumo eléctrico por recibo o inventario, estimación de número de paneles, energía, ahorro y retorno simple. Descarga un resumen `.txt` de la cotización simulada.
- `simulador.html`: laboratorio visual con orientación, irradiancia, sombra uniforme, temperatura y resistencia de carga, gráficas y animación didáctica del efecto fotovoltaico. Clic en el logotipo para regresar a inicio.

## Publicar

1. Descomprimir el ZIP.
2. Subir el **contenido** de la carpeta `A01744151-SOLAR-V3` a la raíz del repositorio, sin una carpeta adicional.
3. Mantener `assets/` como carpeta (no mover sus archivos a la raíz).
4. En GitHub, Settings → Pages → Deploy from branch → main → /(root).
5. Abrir `https://a01744151.github.io/A01744151-SOLAR/` tras completarse el despliegue.

## Importante

- Los seis módulos proceden del conjunto de modelos mostrado por el usuario como referencia; las potencias nominales son de referencia, y las especificaciones eléctricas exactas deben contrastarse con fichas técnicas originales antes de una instalación.
- **Todos los precios son simulados** y editables; no son cotizaciones de proveedores.
- Generación mensual = cantidad × Wp/1000 × horas solares pico × rendimiento × 30 días.
- Cantidad = redondeo hacia arriba de consumo mensual × cobertura objetivo / generación estimada por módulo.
- Ahorro simple = mínimo(consumo, generación) × tarifa introducida. No modela tarifas reales complejas, estacionalidad, exportación de excedentes, cargos fijos, baterías, mantenimiento, impuestos, inflación ni degradación.
- El resumen descargable es un archivo `.txt` y no se presenta como PDF comercial.
- El laboratorio utiliza un **modelo equivalente lineal didáctico**: Isc = (irradiancia efectiva/1000) × (1 + 0.0005 × (temperatura−25)); Voc = 20 × (1−0.0035 × (temperatura−25)) × (0.72 + 0.28 × raíz(irradiancia efectiva/1000)), con Voc=0 en irradiancia nula. La carga resistiva produce I = Isc/(1 + R×Isc/Voc), V=I×R, P=VI. Es una aproximación educativa, no la curva I–V de un módulo real.
- La irradiancia directa proyectada usa máximo(0, cos(ángulo)) y sombra uniforme equivalente; no modela irradiancia difusa ni sombreado parcial.
- No hay información académica de la asignatura visible en el sitio.

## Archivos

`index.html`, `simulador.html`, `styles.css`, `catalogo.js`, `cotizador.js`, `simulador.js`, `.nojekyll`, `assets/`.
