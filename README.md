# Grafo normativo electoral

Visor interactivo del grafo normativo electoral del Paraguay 2026: normas, artículos, notas al pie y las
relaciones entre ellos (modifica, deroga, crea, reglamenta, sanciona). Cada nodo muestra su texto literal y
la página del PDF de donde proviene.

**Sitio:** https://luchobenitez.github.io/grafo-normativo-electoral/

| Documento | Páginas | Nodos | Relaciones |
|---|---|---|---|
| Normativa Electoral Paraguaya 2026 (compendio de la Justicia Electoral) | 556 | 1.473 | 2.228 |
| Folleto CIDEE 2026: Ley N° 834/96 (extractos) | 28 | 85 | 144 |

## Cómo se generó

1. MinerU extrae el texto de cada PDF; una etapa de reparación lo corrige contra la capa de texto del propio
   PDF (palabras pegadas, caracteres mal leídos, líneas omitidas) y registra cada cambio.
2. Un extractor identifica normas, artículos y notas al pie, con su estado de vigencia y su categoría electoral.
3. Un constructor de relaciones aplica la técnica legislativa («Modifícase el Art. 12 de la Ley X» → `MODIFICA_A`).
4. Un auditor valida el esquema, la fidelidad del texto frente a la fuente y la página de cada nodo; solo se
   publica lo que aprueba.

El sitio es un único `index.html` con los datos incrustados (generados el 2026-10-02). Usa
[d3](https://d3js.org) desde cdnjs y la fuente Source Serif 4 de Google Fonts.
