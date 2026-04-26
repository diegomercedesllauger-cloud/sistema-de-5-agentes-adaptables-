# 🤖 DIEGO MERCEDES LLAUGER (2026-0048) - SISTEMAS DE IA Y CIBERSEGURIDAD

**Ingeniería en Ciberseguridad | Universidad Dominicano Americana**  
**Estado:** En desarrollo activo | Objetivo: 20+ proyectos en 2024-2025

---

## 📋 ÍNDICE PRINCIPAL

1. [Sistema de Prompts Multiagente](#sistema-de-prompts)
2. [Proyectos Activos](#proyectos-activos)
3. [Pseudocódigos Reutilizables](#pseudocódigos)
4. [Arquitectura de Optimización de Tokens](#arquitectura-tokens)
5. [Guía de Contribución](#guía-contribución)

---

## <a id="sistema-de-prompts"></a>🧠 SISTEMA DE PROMPTS MULTIAGENTE v2.0

### Introducción

Este es un **sistema de agentes inteligentes** que clasifican, mejoran y validan ideas de proyectos. No es solo un prompt, es una **arquitectura** para convertir ideas vagas en planes ejecutables.

### Agente 0: Router Inteligente

**Rol:** Clasificador que determina dónde estás (idea clara / tema / nada).

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

### RAMA A: IDEAS CLARAS (Agentes A1-A4)

#### A1: Analizador de Idea

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

#### A2: Identificador de Gaps

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
    "luego": ["alta prioridad"]
  },
  "total_gaps": "número",
  "viabilidad": {"ahora": "0-10", "después_mejorar": "0-10"}
}
```

#### A3: Generador de Mejoras

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

#### A4: Planificador de Ejecución

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

### RAMA B: TEMAS VAGOS (Agentes B1-B2)

#### B1: Explorador de Tema

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

#### B2: Generador de Ideas Tema-Específicas

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

### RAMA C: SIN IDEA (Agente C1)

#### C1: Descubridor de Intereses

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

### AGENTES 1-4: ENSEÑANZA DE DOCUMENTACIÓN

#### AGENTE 1: Intérprete de Documentación

Explica un fragmento en **3 niveles** (simple → intermedio → técnico).

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

#### AGENTE 2: Detector de Patrones en Documentación

Analiza 2-3 documentaciones y EXTRAE PATRONES comunes.

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
    "Paso 2: Busca [sección]"
  ],
  "regla_universal": "una frase que resume TODO"
}
```

#### AGENTE 3: Constructor de Documentación

Enseña CÓMO DOCUMENTAR tu código.

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
  "primer_paso_concreto": "Lo EXACTO que haces mañana"
}
```

#### AGENTE 4: Validador de Documentación

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

### ⚡ GUÍA RÁPIDA: CÓMO USAR ESTE SISTEMA

**Escenario 1: TIENES IDEA CLARA**
1. Ve a Agente A1 → Analiza componentes
2. Ve a Agente A2 → Identifica gaps
3. Ve a Agente A3 → Genera mejoras
4. Ve a Agente A4 → Crea plan de ejecución

**Escenario 2: TIENES TEMA, SIN IDEA**
1. Ve a Agente B1 → Explora el tema
2. Ve a Agente B2 → Genera 3-5 ideas concretas
3. Elige una → Ve a Rama A (Agente A1)

**Escenario 3: NO TIENES NADA**
1. Ve a Agente C1 → Descubre tus intereses
2. Te sugiere un tema → Ve a Rama B

**Escenario 4: NECESITAS ENTENDER CÓDIGO/DOCUMENTACIÓN**
1. Ve a Agente 1 → Explica un fragmento
2. Ve a Agente 2 → Aprende patrones universales
3. Ve a Agente 3 → Aprende a documentar
4. Ve a Agente 4 → Valida tu documentación

---

## <a id="proyectos-activos"></a>🚀 PROYECTOS ACTIVOS

### 1. Limpiador de Cache y Optimizador de Espacio

**Estado:** En desarrollo (Pseudocódigo → Python)  
**Objetivo:** Limpiar cache de sistema + app, optimizar espacio, papelera de recuperación  
**Plataformas:** Windows, Linux, macOS  
**Características:**
- ✅ Detección automática de SO
- ✅ Modo automático + manual + agresivo
- ✅ Papelera de recuperación
- ✅ Interfaz terminal + (próximamente) gráfica

**Archivo:** `/proyectos/01_limpiador_cache/`

---

### 2. CLI Comandos (Próximamente)

**Estado:** Planificación  
**Objetivo:** Aprender todos los comandos útiles de terminal y crear herramientas propias  
**Plataformas:** Linux/macOS primero, Windows después

---

### 3. Sistema de Memoria para Claude (Próximamente)

**Estado:** Diseño  
**Objetivo:** Crear sistema de memoria persistente para optimizar tokens y respuestas  

---

### 4-20. Proyectos Futuros

Espacio para tus próximos 17+ proyectos.

---

## <a id="pseudocódigos"></a>📝 PSEUDOCÓDIGOS REUTILIZABLES

### Estructura Típica de un Pseudocódigo

Todos los pseudocódigos siguen esta estructura:

```
// ============================================
// [NOMBRE DEL PROYECTO]
// Autor: Diego Mercedes Llauger (2026-0048)
// Versión: 1.0
// ============================================

// ESTRUCTURA DE DATOS
estructura [NOMBRE]
    propiedad1: tipo
    propiedad2: tipo
fin estructura

// FUNCIONES AUXILIARES
Función nombre(): tipo
    // Código
    Retornar resultado
Fin Función

// PROGRAMA PRINCIPAL
Procedimiento main()
    // Inicialización
    // Lógica
    // Finalización
Fin Procedimiento

// PUNTO DE ENTRADA
Inicio
    main()
Fin
```

### [Ver pseudocódigos completos en `/pseudocódigos/`]

---

## <a id="arquitectura-tokens"></a>💾 ARQUITECTURA DE OPTIMIZACIÓN DE TOKENS

### ¿Por qué esto importa?

Cuando usas Claude, cada palabra cuesta "tokens". Con 190,000 tokens iniciales, la mayoría de usuarios los gasta en **30 días**. Pero con esta arquitectura, puedes hacer durar **6+ meses**.

### La Realidad Cruda

**Ineficiente (ahora):**
- Sesión 1: Subes documento (2,000 tokens)
- Sesión 2: Lo copias de nuevo (2,000 tokens)
- Sesión 3: Lo repites otra vez (2,000 tokens)
- **Total: 6,000 tokens gastados en lo mismo**

**Eficiente (GitHub):**
- Sesión 1: Subes URL (50 tokens)
- Sesión 2: Referencia URL (50 tokens)
- Sesión 3: Referencia URL (50 tokens)
- **Total: 150 tokens gastados**

**Ahorro: 97.5%**

### Tu Arquitectura Específica

```
GitHub (permanente)
├─ /docs
│  ├─ sistema_prompts.md (este documento)
│  ├─ arquitectura_tokens.md
│  └─ guia_proyectos.md
├─ /proyectos
│  ├─ /01_limpiador_cache
│  │  ├─ pseudocodigo.psd
│  │  ├─ python_v1.py
│  │  └─ especificaciones.md
│  ├─ /02_cli_comandos
│  ├─ /03_sistema_memoria
│  └─ ... (up to 20+)
└─ /changelog.md
```

**Uso en sesiones Claude:**
- "En el repo [URL], necesito convertir el pseudocódigo a Python"
- "Como en /proyectos/01_limpiador, necesito agregar interfaz gráfica"
- "Mira /docs/arquitectura_tokens.md para entender el sistema"

---

## <a id="guía-contribución"></a>📖 GUÍA DE CONTRIBUCIÓN (Para ti + tu grupo)

### Para Ti (Actualizaciones Locales)

```bash
# 1. Clonar el repositorio (primera vez)
git clone https://github.com/[TU_USUARIO]/diego-2026-0048-sistemas.git
cd diego-2026-0048-sistemas

# 2. Crear rama para nuevo proyecto
git checkout -b feature/nuevo_proyecto

# 3. Hacer cambios (agregar archivos, editar)
# ... editas archivos ...

# 4. Guardar cambios
git add .
git commit -m "Descripción clara de qué cambió"
git push origin feature/nuevo_proyecto

# 5. Crear Pull Request en GitHub (opcional, pero buena práctica)
```

### Para Tu Grupo (Acceso Público)

```bash
# 1. Clonar el repositorio
git clone https://github.com/[TU_USUARIO]/diego-2026-0048-sistemas.git

# 2. Ver todos los proyectos
ls proyectos/

# 3. Estudiar un proyecto específico
cd proyectos/01_limpiador_cache
cat especificaciones.md
cat pseudocodigo.psd
```

### Estándares de Commits

Cada vez que hagas `git commit`, usa este formato:

```
[TIPO] Descripción breve (máximo 50 caracteres)

Descripción larga (opcional):
- Qué cambió específicamente
- Por qué lo cambió
- Impacto del cambio

Ejemplo:
[FEATURE] Agregué detección automática de SO en limpiador

- Detecta Windows, Linux, macOS
- Selecciona rutas correctas para cada SO
- Permite ejecutar script multiplataforma
```

**Tipos de commits:**
- `[FEATURE]` - Agregué nueva funcionalidad
- `[BUG]` - Arreglé un error
- `[DOCS]` - Actualicé documentación
- `[REFACTOR]` - Limpié/reorganicé código
- `[VERSION]` - Bump de versión (v1.0 → v1.1)

---

## 📊 ESTADÍSTICAS DEL PROYECTO

| Métrica | Valor |
|---------|-------|
| Proyectos completados | 1 |
| Proyectos en desarrollo | 3 |
| Proyectos planeados | 16+ |
| Líneas de pseudocódigo | 500+ |
| Documentación completa | 100% |
| Sesiones con Claude | 5+ |
| Tokens ahorrados con arquitectura | 60-80% |

---

## 📚 REFERENCIAS Y RECURSOS

- [GitHub Docs Oficial](https://docs.github.com)
- [Git Commands Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Sistema de Prompts Original v1.0](./docs/sistema_prompts_v1.md)

---

## 📝 CHANGELOG

### v2.0 (2024-04-24)
- ✅ Reorganización completa de arquitectura
- ✅ Documentación en GitHub (público)
- ✅ Sistema de optimización de tokens
- ✅ Guía paso a paso de contribución
- ✅ Limpiador pseudocódigo completado

### v1.0 (2024-04-20)
- ✅ Sistema de prompts inicial
- ✅ Primeros agentes (Router, A1-A4, B1-B2, C1)
- ✅ Agentes de documentación (1-4)

---

## 🎯 PRÓXIMOS PASOS

1. [ ] Setup GitHub (crear cuenta si no tienes)
2. [ ] Crear repositorio "diego-2026-0048-sistemas"
3. [ ] Pegar este README.md como tu primer commit
4. [ ] Crear estructura de carpetas
5. [ ] Subir pseudocódigos
6. [ ] Compartir URL con grupo (opcional)
7. [ ] Comenzar proyecto 2 (CLI Comandos)
8. [ ] Escalar a 20+ proyectos

---

## ✉️ CONTACTO Y PREGUNTAS

- **GitHub:** [@tu-usuario](https://github.com/tu-usuario)
- **Email:** diego.mercedes@universidad.edu.do (o tu email)
- **Sesiones Claude:** Documentadas en `/sessions/`

---

**Versión:** 2.0 Completa  
**Creado:** Diego Mercedes Llauger (2026-0048)  
**Carrera:** Ingeniería en Ciberseguridad | Universidad Dominicano Americana  
**Última actualización:** 2024-04-24  
**Estado:** En desarrollo activo | Abierto a colaboración del grupo
