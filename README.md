# ProcesaMiniAOD-Noviembre2026

# Set de señales v1 (borrador, pendiente de congelar)

Fecha: 2026-11-16. Se anota antes de mirar cualquier AUC, para que la elección de señales no dependa de los resultados.

## Cuadrícula 3 familias x 3 masas (pT del jet de señal ≈ 1 / 1.5 / 2.5 TeV)

| Familia | M = 2000 (pT ≈ 1 TeV) | M = 3000 (pT ≈ 1.5 TeV) | M = 5000 (pT ≈ 2.5 TeV) |
|---|---|---|---|
| Bulk graviton WW→4q | record 33702 (eventos/archivos por anotar) | por anotar | 136 000 ev., 21 archivos, 9.4 GiB |
| W′ ggF → WZ (W had., Z lep.) | 23 000 ev., 2 archivos, 1.3 GiB (MiniAOD por anotar; NanoAOD 71497) | 23 000 ev., 7 archivos, 1.4 GiB (MiniAOD por anotar; NanoAOD 71501) | record 71508: 23 000 ev., 3 archivos, 1.4 GiB |
| X→YY′→4q, MY=80, MY′=25 | record 73213: 23 000 ev., 1 archivo, 1.1 GiB (fragmento 02593) | record 73349: 23 000 ev., 1 archivo, 1.2 GiB (fragmento 02605) | record 73601: 23 000 ev., 4 archivos, 1.5 GiB (fragmento 02617) |

Todas: UL16 MiniAODv2, 106X_mcRun2_asymptotic_v17, TuneCP5 (en el nombre).

## Reglas de etiquetado
- Bulk y W′: etiqueta truth = W hadrónico (PDG 24), con los dos quarks dentro del jet AK8.
- X→YY′: etiqueta truth = partícula PDG 23 (masa generada 80 GeV, según el fragmento). El PDG 25 (25 GeV) se descarta. Confirmar con la masa generada en GenParticles antes de usarlo.
- Selección siempre por truth, nunca por SDMass reco (evita esculpir la señal a favor de los baselines de masa).
- Los jets del evento sin etiqueta no se reutilizan como QCD ni como señal.
- `pt_min` común a QCD y a todas las señales. Bootstrap por evento.

## Estado de verificación
- Tune: los 3 fragmentos X→YY′ (02593, 02605, 02617) usan pythia8CP5Settings (según resumen del fetch; releer el texto literal). Bulk y W′: CP5 solo por el nombre.
- Y/Y′ decaen solo a u, d, s con peso igual (jet de 80 de quarks ligeros).

## Pendiente
- Records MiniAOD del Bulk M2000 y M3000 y de los W′ M2000 y M3000.
- Comprobar en GenParticles qué PDG (23 o 25) tiene masa 80.
- Paso 0 de la hoja de ruta (m9001, estado del Bulk M4000/M5000, `pt_min`) y script que genera `ae_dataset-*.csv`.

## Fuera del set principal (limitaciones del paper)
- tt̄ (TTToHadronic, ttH): a ese pT el jet es mayormente un top, y la etiqueta de W limpio es difícil.
- X→YY′ MX4000_MY60_MYprime90: ninguno de sus jets tiene masa 80.
- Z′→tt: usa TuneCP2.
