# 🤖 SISTEMA DE PROMPTS MULTIAGENTE - DIEGO MERCEDES LLAUGER (2026-0048)
**Ingeniería en Ciberseguridad | Universidad Dominicano Americana**

---

## 📋 ÍNDICE RÁPIDO
- [Agente 0: Router](#router) - Clasificador de ideas
- [Rama A: Ideas claras](#rama-a) - Mejora de ideas
- [Rama B: Temas vagos](#rama-b) - Generación de ideas
- [Rama C: Sin idea](#rama-c) - Descubrimiento
- [Agentes 1-4: Documentación](#doc) - Enseñanza de código
- [Comandos útiles](#comandos)

---

## <a id="router"></a>🚪 AGENTE 0: ROUTER INTELIGENTE

**Rol:** Clasificador que determina dónde estás tú (idea clara / tema / nada).

**Entrada:** Lo que describes
**Salida:** JSON + siguiente agente

```json
{
  "clasificación": "RAMA_A|RAMA_B|RAMA_C",
  "veredicto": "El usuario está en [rama]",
  "confianza": "0-10",
  "próximo_paso": "Ir a Agente [A1|B1|C1]",
  "lo_que_falta": "qué información es útil",
  "observación": "Tu análisis"
}
```

**Regla simple:**
- **RAMA A:** Tienes idea + tema claro → MEJORAR
- **RAMA B:** Tienes tema, idea vaga → GENERAR IDEAS
- **RAMA C:** Nada → DESCUBRIR INTERESES

---

## <a id="rama-a"></a>🎯 RAMA A: IDEAS CLARAS (Agentes A1-A4)

### A1: Analizador de Idea
Descompone tu idea en componentes (problema, solución, audiencia).

```json
{
  "idea_original": "tu idea",
  "componentes": [
    {"componente": "problema", "está_claro": true/false, "nivel": "0-10"}
  ],
  "estructura_de_idea": {
    "problema_que_resuelve": "?",
    "solución_propuesta": "?",
    "audiencia_objetivo": "?",
    "diferenciador": "?",
    "restricciones_conocidas": ["lista"]
  },
  "claridad_general": "0-10",
  "puntos_fuertes": ["..."],
  "puntos_vagos": ["..."],
  "está_lista_para_mejorar": true/false
}
```

### A2: Identificador de Gaps
Encuentra exactamente qué falta.

```json
{
  "gaps_identificados": [
    {
      "gap": "qué falta",
      "severidad": "crítica|alta|media|baja",
      "solución_preliminar": "idea inicial"
    }
  ],
  "priorización": {
    "arreglar_primero": ["gap crítico"],
    "luego": ["alta prioridad"],
    "después": ["media prioridad"]
  },
  "total_gaps": "número",
  "viabilidad": {"ahora": "0-10", "después_mejorar": "0-10"}
}
```

### A3: Generador de Mejoras
Propone mejoras específicas para cada gap.

```json
{
  "mejoras_propuestas": [
    {
      "gap_que_arregla": "cuál",
      "mejora": "qué cambiar",
      "dificultad": "baja|media|alta",
      "impacto": "0-10"
    }
  ],
  "idea_mejorada": {
    "resumen": "idea final",
    "cambios_principales": ["lista"],
    "mantiene_esencia": true
  },
  "validación": {
    "todas_viables": true,
    "requiere_recursos": true/false,
    "es_escalable": true/false
  }
}
```

### A4: Planificador de Ejecución
Convierte idea en **plan paso a paso**.

```json
{
  "idea_a_ejecutar": "resumen",
  "objetivo_final": "qué lograr",
  "plan_general": {"fases": "número", "duración_total": "tiempo"},
  "plan_detallado": [
    {
      "fase": 1,
      "nombre": "nombre fase",
      "objetivo": "qué se logra",
      "hitos": [
        {
          "hito": "descripción",
          "duración": "tiempo",
          "entrega": "qué se produce"
        }
      ],
      "criterio_éxito": "cómo saber que está listo"
    }
  ],
  "primer_paso": "Lo EXACTO que haces mañana"
}
```

---

## <a id="rama-b"></a>💡 RAMA B: TEMAS VAGOS (Agentes B1-B2)

### B1: Explorador de Tema
Descompone un tema en ángulos de proyecto viables.

```json
{
  "tema_original": "el tema",
  "descomposición": [
    {
      "subtema": "parte específica",
      "descripción": "qué abarca",
      "oportunidades_proyecto": ["idea 1", "idea 2"]
    }
  ],
  "ángulos_posibles": [
    {
      "ángulo": "perspectiva",
      "nivel_dificultad": "principiante|intermedio|avanzado",
      "tiempo_estimado": "rango",
      "por_qué_viable": "razón"
    }
  ],
  "tendencias_actuales": ["trend 1"],
  "gaps_en_tema": ["área poco explorada"],
  "recomendación": "ángulos más viables"
}
```

### B2: Generador de Ideas Tema-Específicas
Crea **3-5 ideas concretas** del tema.

```json
{
  "tema_base": "el tema",
  "ideas_generadas": [
    {
      "número": 1,
      "nombre": "nombre atractivo",
      "descripción": "qué es",
      "detalles": {
        "objetivo": "qué lograr",
        "problema_que_resuelve": "cuál",
        "solución": "cómo lo soluciona"
      },
      "viabilidad": {
        "dificultad": "baja|media|alta",
        "tiempo_estimado": "rango",
        "es_escalable": true/false
      },
      "si_la_hicieras": "qué aprenderías"
    }
  ],
  "comparación_rápida": {
    "más_rápida": "cuál",
    "más_impactante": "cuál",
    "más_fácil": "cuál",
    "más_aprendizaje": "cuál"
  },
  "recomendación": "cuál es mejor para ti"
}
```

---

## <a id="rama-c"></a>🔍 RAMA C: SIN IDEA (Agente C1)

### C1: Descubridor de Intereses
Encuentra qué te interesa REALMENTE.

```json
{
  "situación_usuario": "sin idea ni tema",
  "preguntas_que_haría": [
    {
      "pregunta": "qué pregunta?",
      "por_qué": "por qué revela interés"
    }
  ],
  "patrones_de_interés": [
    {
      "patrón": "tipo de cosa",
      "evidencia": "cómo lo identificaste",
      "proyectos_posibles": ["idea 1"]
    }
  ],
  "áreas_posibles": [
    {
      "área": "temática",
      "por_qué_podría_interesar": "razón",
      "proyectos_iniciales": ["idea 1"]
    }
  ],
  "próximo_paso": "Ir a Agente B1 con [tema sugerido]"
}
```

---

## <a id="doc"></a>📚 AGENTES 1-4: ENSEÑANZA DE DOCUMENTACIÓN

Para aprender a **leer, entender y escribir documentación técnica**.

### AGENTE 1: Intérprete de Documentación
Explica un fragmento en **3 niveles** (simple → intermedio → técnico).

**Entrada:** Fragmento de doc que NO entiendes
**Salida:** Explicación progresiva

```json
{
  "fragmento_original": "el texto",
  "título_tema": "qué tema",
  "nivel_1_simple": {
    "explicación_cotidiana": "analogía día a día",
    "en_palabras_simples": "sin tecnicismos",
    "para_qué_sirve": "por qué existe"
  },
  "nivel_2_intermedio": {
    "términos_nuevos": [
      {"término": "palabra", "qué_es": "definición", "en_contexto": "cómo se usa"}
    ],
    "explicación_con_términos": "ahora con jerga"
  },
  "nivel_3_técnico": {
    "explicación_completa": "lenguaje técnico",
    "detalles_avanzados": ["aspecto 1"]
  },
  "ejemplo_práctico": {
    "código": "ejemplo simple",
    "qué_hace": "línea por línea",
    "resultado": "qué esperas"
  },
  "errores_frecuentes": [
    {
      "error": "equivocación típica",
      "por_qué": "razón",
      "cómo_evitarlo": "solución"
    }
  ],
  "idea_clave": "LO MÁS IMPORTANTE"
}
```

### AGENTE 2: Detector de Patrones en Documentación
Analiza **2-3 documentaciones** y EXTRAE PATRONES comunes.

```json
{
  "documentaciones_analizadas": "de dónde",
  "patrones_encontrados": [
    {
      "patrón": "nombre",
      "descripción": "qué es",
      "aparece_en": ["doc 1", "doc 2"],
      "por_qué_existe": "razón lógica",
      "dónde_buscar_rápido": "si necesitas info rápida",
      "ejemplo": "cómo se ve"
    }
  ],
  "estructura_típica_universal": {
    "secciones_siempre_aparecen": ["sección 1"],
    "orden_típico": "orden general",
    "para_entender_rápido": "qué leer primero",
    "para_entender_profundo": "qué leer después"
  },
  "checklist_de_lectura": [
    "Paso 1: Busca [sección]",
    "Paso 2: Busca [sección]",
    "Paso 3: Si necesitas ejemplos, mira [sección]"
  ],
  "regla_universal": "una frase que resume TODO"
}
```

### AGENTE 3: Constructor de Documentación
Enseña CÓMO DOCUMENTAR tu código.

**Entrada:** Tu código
**Salida:** Estructura + plantilla + guía paso a paso

```json
{
  "análisis_del_código": {
    "qué_hace": "descripción",
    "complejidad": "simple|media|compleja",
    "partes_difíciles": ["aspecto 1"]
  },
  "tipo_documentación_necesario": {
    "tipo": "README|API Doc|Code Comments|Guía",
    "por_qué": "razón específica",
    "prioridad_documentación": "qué documentar PRIMERO"
  },
  "estructura_propuesta": {
    "sección_1": {
      "nombre": "nombre exacto",
      "contenido": "ESPECÍFICAMENTE qué va",
      "por_qué": "razón crítica",
      "ejemplo": "cómo se vería"
    }
  },
  "plantilla_copiable": "COPIA Y RELLENA ESTO",
  "guía_paso_a_paso": [
    {
      "paso": 1,
      "acción": "qué hacer",
      "por_qué": "razón",
      "ejemplo": "con tu código real"
    }
  ],
  "errores_típicos_evitar": [
    {"error": "error común", "solución": "cómo no hacerlo"}
  ],
  "primer_paso_concreto": "Lo EXACTO que haces mañana"
}
```

### AGENTE 4: Validador de Documentación
Revisa TU documentación y da **feedback constructivo**.

```json
{
  "resumen": "qué documentación escribiste",
  "evaluación_por_aspecto": {
    "claridad": {
      "score": "0-10",
      "qué_está_claro": ["aspecto 1"],
      "qué_es_confuso": [
        {
          "dónde": "sección específica",
          "por_qué_confunde": "explicación",
          "cómo_arreglarlo": "sugerencia específica"
        }
      ]
    },
    "completitud": {
      "score": "0-10",
      "qué_FALTA": [
        {
          "falta": "qué hace falta",
          "por_qué_importa": "razón",
          "dónde_agregarlo": "sección",
          "ejemplo": "cómo se vería"
        }
      ]
    },
    "ejemplos": {"score": "0-10", "son_ejecutables": true/false},
    "estructura": {"score": "0-10", "es_lógica": true},
    "tono": {"score": "0-10", "es_profesional": true}
  },
  "fortalezas": ["aspecto bien hecho"],
  "mejoras_en_prioridad": [
    {
      "mejora": "qué cambiar",
      "prioridad": "alta|media|baja",
      "cómo_implementar": "pasos concretos"
    }
  ],
  "veredicto_final": "LISTA_PARA_COMPARTIR|NECESITA_AJUSTES|REQUIERE_REVISIÓN"
}
```

---

## <a id="comandos"></a>⚡ GUÍA RÁPIDA: CÓMO USAR ESTE SISTEMA

### Escenario 1: TIENES IDEA CLARA
1. Ve a **Agente A1** → Analiza componentes
2. Ve a **Agente A2** → Identifica gaps
3. Ve a **Agente A3** → Genera mejoras
4. Ve a **Agente A4** → Crea plan de ejecución

### Escenario 2: TIENES TEMA, SIN IDEA
1. Ve a **Agente B1** → Explora el tema
2. Ve a **Agente B2** → Genera 3-5 ideas concretas
3. Elige una → Ve a **Rama A** (Agente A1)

### Escenario 3: NO TIENES NADA
1. Ve a **Agente C1** → Descubre tus intereses
2. Te sugiere un tema → Ve a **Rama B**

### Escenario 4: NECESITAS ENTENDER CÓDIGO/DOCUMENTACIÓN
1. Ve a **Agente 1** → Explica un fragmento
2. Ve a **Agente 2** → Aprende patrones universales
3. Ve a **Agente 3** → Aprende a documentar
4. Ve a **Agente 4** → Valida tu documentación

---

## 📌 EJEMPLO REAL CON TU CÓDIGO

**Tu código tenía problema:** Lógica invertida (ventas >= 5000 = "bajas", cuando debería ser "altas")

**Paso 1 - Agente 1:** 
- Nivel simple: "El código intenta clasificar ventas, PERO la lógica está al revés"
- Nivel intermedio: "≥5000 debería ser ALTO, no BAJO"
- Nivel 3: Booleana invertida

**Paso 2 - Agente 2:**
- Patrón detectado: "7 bucles repetidos idénticamente"
- Regla universal: "Si repites código, refactoriza a 1 bucle que itere 7 veces"

**Paso 3 - Corrección manual:**
```
❌ Para i<-0 Hasta 6 hacer   7 VECES
✅ Para i<-0 Hasta 6 hacer   1 VEZ (con variable que cambia)
```

**Paso 4 - Documentación:**
- Agente 3 → Estructura + plantilla
- Agente 4 → Feedback y validación

---

## 🎓 CLAVE PARA APRENDER

> **No memorizas los agentes. USAS los agentes para aprender PATRONES.**

Cada vez que uses uno:
1. Entiende POR QUÉ esa estructura funciona
2. Identifica el PATRÓN (aplica a otros proyectos)
3. Aplica el patrón a nuevas tareas

---

**Versión:** 2.0 Compacta
**Creado:** Diego Mercedes Llauger (2026-0048)
**Carrera:** Ingeniería en Ciberseguridad | Universidad Dominicano Americana
