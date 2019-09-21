# Resumen

Acontinuación se realizará una predicción de remuneraciones de futbolistas a partir de estadísticas sobre sus habilidades de juego. Para ellos se filtrarán los datos de habilidades y se realizará un análisis exploratorio para identificar patrones en los datos que permitan tener información fiable e implementar una predicción mediante una regresión lineal en tensorflow.

# Antecedentes de los datos

Los datos son estadísticas del juego Fifa 19 con los principales equipos y jugadores de fútbol del mundo. La base de datos se encuentran en https://www.kaggle.com/karangadiya/fifa19.

Estos datos fueron extraídos desde https://sofifa.com/.

Para este análisis se utilizarán sólo las variables relacionadas a habilidades específicas de los jugadores:

Información de los atributos:

- **Wage**: Remuneración de los futbolistas (EUR).
- **LS (Left Striker)**: Habilidad en la posición (0-99).
- **ST (Striker)**: Habilidad en la posición (0-99).
- **RS (Right Striker)**: Habilidad en la posición (0-99).
- **LW (Left Wing)**: Habilidad en la posición (0-99).
- **LF (Left Forward)**: Habilidad en la posición (0-99).
- **CF (Center Forward)**: Habilidad en la posición (0-99).
- **RF (Right Forward)**: Habilidad en la posición (0-99).
- **RW (Right Wing)**: Habilidad en la posición (0-99).
- **LAM (Left Attacking Midfielder)**: Habilidad en la posición (0-99).
- **CAM (Center Attacking Midfielder)**: Habilidad en la posición (0-99).
- **RAM (Right Attacking Midfielder)**: Habilidad en la posición (0-99).
- **LM (Left Midfielder)**: Habilidad en la posición (0-99).
- **LCM (Left Center Midfielder)**: Habilidad en la posición (0-99).
- **CM (Center Midfielder)**: Habilidad en la posición (0-99).
- **RCM (Right Center Midfielder)**: Habilidad en la posición (0-99).
- **RM (Right Midfielder)**: Habilidad en la posición (0-99).
- **LWB (Lef Wing Back)**: Habilidad en la posición (0-99).
- **LDM (Left Defensive Midfielder)**: Habilidad en la posición (0-99).
- **CDM (Center Defensive Midfielder)**: Habilidad en la posición (0-99).
- **RDM (Right Defensive Midfielder)**: Habilidad en la posición (0-99).
- **RWB (Right Wing Back)**: Habilidad en la posición (0-99).
- **LB (Lef Back)**: Habilidad en la posición (0-99).
- **LCB (Left Center Back)**: Habilidad en la posición (0-99).
- **CB (Center Back)**: Habilidad en la posición (0-99).
- **RCB (Right Center Back)**: Habilidad en la posición (0-99).
- **RB (Right Back)**: Habilidad en la posición (0-99).
- **Crossing**: Ofensiva, habilidad en centros (0-99).
- **Finishing**: Ofensiva, habilidad en definición (0-99).
- **HeadingAccuracy**: Ofensiva, precisión con la cabeza (0-99).
- **ShortPassing**: Ofensiva, habilidad en pases cortos (0-99).
- **Volleys**: Ofensiva, habilidad en voleas (0-99).
- **Dribbling**: Técnica, habilidad en regates (0-99).
- **Curve**: Técnica, habilidad en balones con efecto (0-99).
- **FKAccuracy**: Técnica, habilidad en precisión faltas (0-99).
- **LongPassing**: Técnica, habilidad en pases largos (0-99).
- **BallControl**: Técnica, habilidad en control del balón (0-99).
- **Acceleration**: Movimiento, aceleración (0-99).
- **SprintSpeed**: Movimiento, velocidad (0-99).
- **Agility**: Movimiento, agilidad (0-99).
- **Reactions**: Movimiento, reflejos (0-99).
- **Balance**: Movimiento, equilibrio (0-99).
- **ShotPower**: Potencia, potencia (0-99).
- **Jumping**: Potencia, salto (0-99).
- **Stamina**: Potencia, resistencia (0-99).
- **Strength**: Potencia, fuerza (0-99).
- **LongShots**: Potencia, tiros lejanos (0-99).
- **Aggression**: Mentalidad, agresividad (0-99).
- **Interceptions**: Mentalidad, intercepción (0-99).
- **Positioning**: Mentalidad, colocación (0-99).
- **Vision**: Mentalidad, visión (0-99).
- **Penalties**: Mentalidad, penales (0-99).
- **Composure**: Mentalidad, compostura (0-99).
- **Marking**: Defensa, marcaje (0-99)
- **StandingTackle**: Defensa, robos (0-99)
- **SlidingTackle**: Defensa, entrada agresiva (0-99)
- **GKDiving**: Portero, estirada (0-99)
- **GKHandling**: Portero, paradas (0-99)
- **GKKicking**: Portero, saques (0-99)
- **GKPositioning**: Portero, colocación (0-99)
- **GKReflexes**: Portero, reflejos (0-99)
- **Release Clause**: Clausula de liberación, en EU.


---

Link Rpubs: http://rpubs.com/desareca/Prediccion-Sueldos-Futbolistas

