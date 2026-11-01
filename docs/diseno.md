# Veta — diseño de oficios

Juego de progresión basado en oficios artesanales entrelazados de forma realista.
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

## Sistemas a considerar
- Temperatura máxima de los hornos según combustible y fuelle.
- Tiempos reales (secado de madera, curtido, carboneras).
- Calidad y pureza (ley, quilates, nudos, inclusiones; dureza de Mohs).
- Desgaste de herramientas.
- Energía hidráulica (molinos, martinetes, fuelles).
- Comercio y rutas para materiales exóticos (ébano, lapislázuli, nácar, cochinilla).
- Gremios y rangos: aprendiz → oficial → maestro, con obra maestra.
- Subproductos con uso (escoria, serrín, recortes, ceniza).

## Aparcado para el futuro
- **Relojería**: acero de muelles, latón, rubíes (Lapidaria), vidrio, esmalte, caja de madera noble.
- **Luthería**: abeto y arce de secado largo, ébano, cola animal, barniz, tripa, alambre de latón.
