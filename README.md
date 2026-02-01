# Actividad de Laboratorio – Implementación de Audio en Unreal Engine y FMOD

## Entrega
Además de este memoría se facilitan los enlaces a:
* Un vídeo explicativo: https://drive.google.com/file/d/1R18hkFob8dFZzL4bWfG9LXIlqevqWeeX/view?usp=sharing 
* Repositorio que incluye proyecto de FMOD y de Unreal:
https://github.com/raimonunir/Actividad3Sonido 

## Descripción general

Este proyecto corresponde a la **Actividad de Laboratorio de Implementación de Audio en Unreal Engine y FMOD**, cuyo objetivo principal es demostrar la integración de un sistema de audio dinámico para un videojuego en tercera persona, aplicando técnicas de diseño de sonido vistas en clase.

Todo el sistema de sonido ha sido **diseñado e implementado desde cero**, incluyendo la creación de eventos, parámetros, lógica interactiva y ambientación dinámica en función del estado del mundo y las acciones del jugador.

---

## Objetivos de la actividad

* Implementar audio dinámico utilizando **FMOD Studio** integrado en **Unreal Engine**.
* Crear y configurar eventos de sonido con variaciones mediante parámetros.
* Diseñar un paisaje sonoro coherente con el entorno y el gameplay.
* Integrar correctamente los eventos de FMOD en Blueprints de Unreal Engine.
* Validar el correcto funcionamiento del sistema de audio mediante pruebas en un mapa jugable.

---

## Versiones utilizadas

* **Unreal Engine:** 5.4.4
* **FMOD Studio:** 2.03.12
* **Integración FMOD–Unreal:** Plugin oficial compatible con UE 5.4

---

## Escenario y contexto

El proyecto utiliza como base un **mapa de tercera persona**, adaptado para crear un entorno natural con elementos interactivos y ambientales. Se ha incorporado un personaje que encaja visual y narrativamente con el escenario.

El diseño sonoro busca reforzar la inmersión mediante:

* Sonidos ambientales dinámicos.
* Respuesta sonora a las acciones del jugador.
* Uso extensivo de parámetros, atenuación y modulación.

---

## Sistema de audio implementado

### 1. Audio ambiental y ciclo Día/Noche

Se ha implementado un **ciclo dinámico de Día/Noche**, que modifica el paisaje sonoro del entorno:

* **Durante el día:**

  * Ambiente ventoso.
  * Sonidos naturales diurnos.

* **Durante la noche:**

  * Sonido de grillos.
  * Ambiente nocturno más calmado.

La transición entre estados se realiza mediante **eventos con loop regions y fade in / fade out**, garantizando cambios suaves y naturales.

#### Antorchas

* Las antorchas:

  * **Dejan de sonar durante el día**.
  * **Comienzan a sonar durante la noche**.
* La activación y desactivación del sonido está controlada mediante lógica en Blueprints y eventos de FMOD.

---

### 2. Sonidos interactivos

Se han implementado distintos sonidos interactivos que responden directamente a acciones del jugador:

* **Hoguera del pez**

  * Al ser activada por el personaje, comienza la reproducción del sonido de fuego.

* **Comer manzana**

  * Blueprint creado desde cero.
  * Reproduce un evento específico de interacción al consumir el objeto.

---

### 3. Pasos y movimiento del personaje

El sistema de movimiento del personaje incluye un **sistema de pasos avanzado** basado en el sistema visto en clase:

* Pasos diferenciados según el tipo de superficie:

  * Roca
  * Madera
  * Tierra
  * Hierba

* Cada evento de pasos utiliza:

  * **Multinstrument con Shuffle**.
  * **Add Modulation** tanto en:

    * Pitch
    * Volumen

Esto permite evitar la repetición perceptible y añade naturalidad al movimiento.

#### Saltos

* Se ha implementado un **sonido de salto específico para cada tipo de superficie**, coherente con el sistema de pasos.

---

### 4. Sonidos ambientales específicos

Además del ambiente general, se han añadido sonidos localizados:

* **Molino de viento**
* **Agua del lago**
* **Pozo**

Estos sonidos utilizan **atenuación espacial**, tal y como se explicó en clase, para reforzar la percepción de distancia y posición en el mundo.

---

### 5. Uso de FMOD

El proyecto hace un uso extensivo de las herramientas de FMOD Studio:

* Creación de eventos independientes por tipo de sonido.
* Uso de **parámetros** para controlar estados y variaciones.
* Loop regions para sonidos continuos.
* Fade in / fade out para transiciones suaves.
* Atenuación aplicada a sonidos ambientales e interactivos.

---

## Integración en Unreal Engine

* El proyecto de **FMOD Studio** se encuentra dentro de la carpeta del proyecto de Unreal Engine.
* Los bancos y eventos han sido correctamente generados e importados.
* La reproducción de sonido se gestiona mediante **Blueprints**, respondiendo a:

  * Acciones del jugador.
  * Estados del entorno (día/noche).
  * Proximidad a objetos sonoros.

---

## Pruebas

Se ha validado que:

* Todos los eventos se reproducen correctamente.
* Los sonidos reaccionan a las interacciones del jugador.
* El sistema de día/noche altera correctamente el paisaje sonoro.
* La atenuación y espacialización funcionan según lo esperado.

---

## Entrega

La entrega de la actividad consta de:

1. **Vídeo** mostrando la implementación del sistema de audio en funcionamiento dentro del mapa de Unreal Engine.
2. **Este repositorio** que contiene:

   * El proyecto completo de Unreal Engine.
   * La carpeta del proyecto de FMOD Studio integrada en su interior.

---

## Recursos utilizados

* Freesound.org – Biblioteca de sonidos gratuitos.
* BBC Sound Effects Library – Biblioteca de efectos de sonido gratuita.

---

## Observaciones finales

Este proyecto demuestra la implementación completa de un sistema de audio dinámico e interactivo, integrando FMOD y Unreal Engine de forma profesional, aplicando criterios de diseño sonoro orientados a videojuegos y respetando las buenas prácticas vistas durante el curso.
