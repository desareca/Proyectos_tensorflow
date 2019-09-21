# Resumen

Acontinuación se realizará una predicción de remuneraciones de futbolistas a partir de estadísticas sobre sus habilidades de juego. Para ellos se filtrarán los datos de habilidades y se realizará un análisis exploratorio para identificar patrones en los datos que permitan tener información fiable e implementar una predicción mediante una regresión lineal en tensorflow.

# Antecedentes de los datos

Los datos son estadísticas del juego Fifa 19 con los principales equipos y jugadores de fútbol del mundo. La base de datos se encuentran en https://www.kaggle.com/karangadiya/fifa19.

Estos datos fueron extraídos desde https://sofifa.com/.

Para este análisis se utilizarán sólo las variables relacionadas a habilidades específicas de los jugadores:

Información de los atributos:
||||
---|---|---
|<div style="text-align: left">**LS (Left Striker)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**ST (Striker)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**RS (Right Striker)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**LW (Left Wing)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**LF (Left Forward)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**CF (Center Forward)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**RF (Right Forward)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**RW (Right Wing)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**LAM (Left Attacking Midfielder)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**CAM (Center Attacking Midfielder)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**RAM (Right Attacking Midfielder)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**LM (Left Midfielder)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**LCM (Left Center Midfielder)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**CM (Center Midfielder)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**RCM (Right Center Midfielder)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**RM (Right Midfielder)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**LWB (Lef Wing Back)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**LDM (Left Defensive Midfielder)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**CDM (Center Defensive Midfielder)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**RDM (Right Defensive Midfielder)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**RWB (Right Wing Back)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**LB (Lef Back)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**LCB (Left Center Back)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**CB (Center Back)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**RCB (Right Center Back)**: Habilidad en la posición (0-99).<div/>|<div style="text-align: left">**RB (Right Back)**: Habilidad en la posición (0-99).<div/>
|<div style="text-align: left">**Crossing**: Ofensiva, habilidad en centros (0-99).<div/>|<div style="text-align: left">**Finishing**: Ofensiva, habilidad en definición (0-99).<div/>
|<div style="text-align: left">**HeadingAccuracy**: Ofensiva, precisión con la cabeza (0-99).<div/>|<div style="text-align: left">**ShortPassing**: Ofensiva, habilidad en pases cortos (0-99).|<div/>
|<div style="text-align: left">**Volleys**: Ofensiva, habilidad en voleas (0-99).<div/>|<div style="text-align: left">**Dribbling**: Técnica, habilidad en regates (0-99).|<div/>
|<div style="text-align: left">**Curve**: Técnica, habilidad en balones con efecto (0-99).<div/>|<div style="text-align: left">**FKAccuracy**: Técnica, habilidad en precisión faltas (0-99).|<div/>
|<div style="text-align: left">**LongPassing**: Técnica, habilidad en pases largos (0-99).<div/>|<div style="text-align: left">**BallControl**: Técnica, habilidad en control del balón (0-99).|<div/>
|<div style="text-align: left">**Acceleration**: Movimiento, aceleración (0-99).<div/>|<div style="text-align: left">**SprintSpeed**: Movimiento, velocidad (0-99).|<div/>
|<div style="text-align: left">**Agility**: Movimiento, agilidad (0-99).<div/>|<div style="text-align: left">**Reactions**: Movimiento, reflejos (0-99).|<div/>
|<div style="text-align: left">**Balance**: Movimiento, equilibrio (0-99).<div/>|<div style="text-align: left">**ShotPower**: Potencia, potencia (0-99).|<div/>
|<div style="text-align: left">**Jumping**: Potencia, salto (0-99).<div/>|<div style="text-align: left">**Stamina**: Potencia, resistencia (0-99).|<div/>
|<div style="text-align: left">**Strength**: Potencia, fuerza (0-99).<div/>|<div style="text-align: left">**LongShots**: Potencia, tiros lejanos (0-99).|<div/>
|<div style="text-align: left">**Aggression**: Mentalidad, agresividad (0-99).<div/>|<div style="text-align: left">**Interceptions**: Mentalidad, intercepción (0-99).|<div/>
|<div style="text-align: left">**Positioning**: Mentalidad, colocación (0-99).<div/>|<div style="text-align: left">**Vision**: Mentalidad, visión (0-99).|<div/>
|<div style="text-align: left">**Penalties**: Mentalidad, penales (0-99).<div/>|<div style="text-align: left">**Composure**: Mentalidad, compostura (0-99).|<div/>
|<div style="text-align: left">**Marking**: Defensa, marcaje (0-99)<div/>|<div style="text-align: left">**StandingTackle**: Defensa, robos (0-99)|<div/>
|<div style="text-align: left">**SlidingTackle**: Defensa, entrada agresiva (0-99)<div/>|<div style="text-align: left">**GKDiving**: Portero, estirada (0-99)|<div/>
|<div style="text-align: left">**GKHandling**: Portero, paradas (0-99)<div/>|<div style="text-align: left">**GKKicking**: Portero, saques (0-99)|<div/>
|<div style="text-align: left">**GKPositioning**: Portero, colocación (0-99)<div/>|<div style="text-align: left">**GKReflexes**: Portero, reflejos (0-99)|<div/>
---

Link Rpubs: http://rpubs.com/desareca/Prediccion-Sueldos-Futbolistas

