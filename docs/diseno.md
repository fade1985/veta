# Veta — diseño de oficios

Juego de progresión basado en oficios artesanales entrelazados de forma realista.
Catálogo de materiales en `docs/catalogo.md`.
El mapa interactivo está en `docs/mapa-oficios.html` (los datos de materiales y
encargos viven en el `<script>` de ese archivo).

## Oficios (19 + Encargos)

| Nivel | Oficios |
|---|---|
| I · Extracción | Minería, Cantería (incluye arcilla, caolín y arena), Silvicultura, Agricultura, Ganadería y caza |
| II · Transformación | Fundición, Calera y yesería, Carbonería, Botica y química, Curtiduría |
| III · Oficios | Herrería, Alfarería y cerámica, Vidriería, Carpintería, Tejeduría y tintorería |
| IV · Maestría | Lapidaria, Orfebrería y joyería, Maestro de obras, Ebanistería |
| Destino | Encargos (clientes) |

### Bucles clave (retornos)
- Herrería → herramientas para todos (se desgastan).
- Alfarería → crisoles, toberas y refractario para fundición, vidriería y orfebrería.
- Curtiduría → cuero para los fuelles de forja y horno.
- Maestro de obras → hornos, molinos y talleres: las mejoras de cada oficio.
- Carpintería → entibos, carros y modelos de fundición.

## Encargos
Clientes (gremios, parroquia, concejo, compañía minera, familias, nobleza) piden
objetos con requisitos de material, calidad y plazo. Recompensas: dinero,
reputación con la facción, recetas y acceso a recursos nuevos.

## Gremios y rangos (un solo artesano)

El jugador es un único artesano. Cada oficio tiene su propia escala de rango;
el rango decide qué puede fabricar, quién le contrata y si tiene taller propio.

### Oficios de gremio
| Rango | Permite | Para subir |
|---|---|---|
| Aprendiz | Recetas básicas, taller y herramientas del maestro, encargos pequeños del taller | Dominar las recetas básicas, tiempo de aprendizaje y examen práctico |
| Oficial | Encargos propios nivel I–II, alquilar banco, viaje de oficial (técnica de otra región) | Viaje hecho, reputación con el gremio, cuota de entrada y obra maestra aprobada por los veedores |
| Maestro | Taller propio, marca personal (más valor), aprendices que producen lo básico solos, encargos III–IV | Fama y años como maestro |
| Veedor | Examinar obras maestras, fijar la calidad mínima, encargos del concejo | Solo en un gremio |

### Oficios libres (Minería, Silvicultura, Agricultura, Ganadería)
Peón → Capataz → Concesionario. El concesionario recibe del concejo su propia
mina, monte o finca, que produce aunque el jugador no esté.

### Reglas
- Un aprendizaje activo a la vez.
- Oficial en 4 gremios como máximo.
- Maestro en 1 gremio al principio; 2 y luego 3 según la fama.
- Inspecciones: una pieza bajo la calidad mínima supone multa y pérdida de reputación; si reincides, expulsión.
- Pleitos entre gremios (p. ej. carpinteros contra ebanistas) como eventos.

### Obras maestras y viajes de oficial
| Oficio | Obra maestra / concesión | Viaje de oficial |
|---|---|---|
| Minería | Registrar una veta nueva y abrir una galería entibada con desagüe | Oficio libre |
| Cantería | Arco de sillería cuyas dovelas encajen sin mortero | Estereotomía |
| Silvicultura | Plan de tala y replantación, y una viga maestra de roble sin nudos | Oficio libre |
| Agricultura | Lino de fibra larga y aceite de linaza claro | Oficio libre |
| Ganadería y caza | Rebaño de lana fina y colmenar estable | Oficio libre |
| Fundición | Plata de ley copelada de galena pobre y bronce sin poros | Beneficio de patio (azogue) |
| Calera y yesería | Cal apagada un año y estuco pulido sin grietas | Estuco de mármol |
| Carbonería | Carbonera de carbón de fragua con alto rendimiento | Hornos de pez |
| Botica y química | Agua fuerte que separe oro de plata | Ultramar y bermellón |
| Curtiduría | Suela curtida un año con corteza y badana fina | Guadamecí |
| Herrería | Juego de herramientas templadas y cerradura de guardas | Damasquinado |
| Alfarería y cerámica | Loza vidriada sin defectos y crisol que aguante tres fundiciones | Mayólica |
| Vidriería | Copa de cristal incoloro y vidrio plano sin burbujas | Vidrio de color y emplomado |
| Carpintería | Armadura de par y nudillo y tonel estanco | Carpintería de lo blanco |
| Tejeduría y tintorería | Paño de lana teñido de grana sin manchas | Teñido con cochinilla |
| Lapidaria | Brillante facetado, cabujón y camafeo | Piedras duras para mosaico |
| Orfebrería y joyería | Cáliz de plata de ley cincelado y con piedras | Filigrana y cloisonné |
| Maestro de obras | Bóveda que se sostenga y horno de 1500 °C | Ruedas hidráulicas y martinetes |
| Ebanistería | Bargueño con taracea, herrajes calados y dorado | Chapeado y marquetería |

## Identificación por pruebas

Los minerales y las gemas no se presentan por su nombre real hasta que el
jugador los identifica. Al extraerlos aparecen por su aspecto: «piedra verde con
bandas», «piedra gris muy pesada en cubitos». El catálogo completo, con aspecto,
raya, dureza y confusiones, está en `catalogo.md`.

### Estados de conocimiento
1. **Desconocido**: solo se ve el aspecto.
2. **Sospechado**: las pruebas dejan pocos candidatos; el juego los muestra.
3. **Identificado**: aparece el nombre real y lo que contiene, p. ej. *Malaquita (cobre)*.
   Desde entonces, ese mineral se reconoce siempre.

Identificar el mineral no dice **cuánta riqueza** tiene esa mena. La riqueza
(ley) solo se conoce con un ensayo a fuego.

### Pruebas (de menos a más fiable)
| Prueba | Requiere | Distingue | Coste |
|---|---|---|---|
| Aspecto | Nada | Color, brillo, forma; poco fiable | Gratis |
| Peso en la mano | Nada | Galena, casiterita y oro pesan mucho | Gratis |
| Raya | Placa de porcelana sin esmaltar (Alfarería) | Hematites (roja), pirita (negra), oro (amarilla), cinabrio (escarlata) | Desgaste de la placa |
| Dureza | Uña (2,5), cobre (3), navaja (5,5), vidrio (5,5), cuarzo (7) | Pirita frente a calcopirita, gemas frente a vidrio | Puede marcar la pieza |
| Imán | Imán natural (magnetita) | Magnetita | Gratis |
| Ácido | Vinagre o agua fuerte (Botica) | Carbonatos que burbujean: malaquita, azurita, calcita, calamina | Gasta reactivo |
| Piedra de toque | Lidita + agua fuerte | Quilates del oro | Gasta reactivo |
| Densidad | Balanza hidrostática (era III) | Gemas y metales preciosos sin dañarlos | Gratis una vez construida |
| Tacto y lupa | Lente (Vidriería) | Vidrio frente a gema, inclusiones, doble imagen | Gratis |
| Ensayo a fuego | Crisol o copela, carbón, horno | Lo que contiene la mena y **su riqueza** | Gasta muestra y combustible |

### Cómo encaja con el resto
- **Minería**: a mayor rango, más minerales se reconocen a simple vista.
- **Botica**: hace las pruebas con ácido y los ensayos; ofrece la tasación como servicio.
- **Lapidaria**: aplica lo mismo a las gemas (espinela o rubí, vidrio o cristal de roca).
- **Errores con consecuencias**: fundir pirita creyendo que es oro, o pagar caro un mineral que es una trampa. Ver la tabla de «minerales trampa» del catálogo.
- **Encargos**: tasar vetas, descubrir fraudes (vellón vendido como plata, dobletes, strass), identificar piedras para coleccionistas.

## Sistemas a considerar
- Temperatura máxima de los hornos según combustible y fuelle.
- Tiempos reales (secado de madera, curtido, carboneras).
- Calidad y pureza (ley, quilates, nudos, inclusiones; dureza de Mohs).
- Desgaste de herramientas.
- Energía hidráulica (molinos, martinetes, fuelles).
- Comercio y rutas para materiales exóticos (ébano, lapislázuli, nácar, cochinilla).
- Subproductos con uso (escoria, serrín, recortes, ceniza).

## Aparcado para el futuro
- **Relojería**: acero de muelles, latón, rubíes (Lapidaria), vidrio, esmalte, caja de madera noble.
- **Luthería**: abeto y arce de secado largo, ébano, cola animal, barniz, tripa, alambre de latón.
