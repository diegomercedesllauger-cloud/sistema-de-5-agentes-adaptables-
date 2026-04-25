# 📋 Especificaciones: Limpiador de Cache y Optimizador de Espacio

**Proyecto:** Limpiador de Cache v1.0  
**Autor:** Diego Mercedes Llauger (2026-0048)  
**Fecha de creación:** 2024-04-24  
**Estado:** En desarrollo (Pseudocódigo → Python)

---

## 📌 DESCRIPCIÓN GENERAL

Sistema automático para limpiar cache, archivos temporales y optimizar espacio en disco. Funciona en Windows, Linux y macOS con detección automática del sistema operativo.

**Objetivo:** Liberar espacio de manera segura, mantener auditoría de limpiezas, permitir recuperación de archivos eliminados.

---

## 🎯 OBJETIVOS PRINCIPALES

1. **Detectar SO automáticamente** → Identifica Windows/Linux/macOS sin intervención
2. **Limpiar cache segura** → Eliminación de archivos que NO son críticos
3. **Modo manual + automático** → Usuario elige qué limpiar o deja que sea automático
4. **Papelera de recuperación** → Los archivos no se borran, se guardan en carpeta de seguridad
5. **Auditoría completa** → LOG de todo lo que se limpió, cuándo, cuánto espacio

---

## ✨ CARACTERÍSTICAS

### Fase 1 (v1.0 - Ahora)
- ✅ Detección automática de SO
- ✅ Modo automático (items seguros)
- ✅ Modo manual (usuario elige)
- ✅ Papelera de recuperación
- ✅ LOG de limpieza
- ✅ Interfaz terminal

### Fase 2 (v1.1 - Próximo)
- ⏳ Modo agresivo (archivos viejos)
- ⏳ Interfaz gráfica
- ⏳ Simulación de limpieza (ver qué se limpiaría sin hacerlo)

### Fase 3 (v2.0 - Futuro)
- ⏳ Programación automática (limpia cada X días)
- ⏳ Estadísticas de uso
- ⏳ Exclusiones personalizables

---

## 🛠️ REQUISITOS TÉCNICOS

### Lenguajes
- **Pseudocódigo:** Pseint (aprendizaje)
- **Python:** 3.8+ (implementación real)

### Dependencias
- `os` (acceso a directorios)
- `shutil` (manejo de archivos)
- `datetime` (timestamps de LOG)
- `platform` (detección de SO)

### Plataformas Soportadas
| SO | Versión | Estado |
|---|---|---|
| Windows | 10, 11 | ✅ Soportado |
| Linux | Ubuntu 18.04+ | ✅ Soportado |
| macOS | 10.14+ | ✅ Soportado |

---

## 📂 ESTRUCTURA DE ARCHIVOS A LIMPIAR

### Windows
```
%TEMP%                                    (Archivos temporales)
C:\Windows\Prefetch                       (Caché de aplicaciones)
$Recycle.Bin                              (Papelera de reciclaje)
%APPDATA%\Local\Google\Chrome\Cache       (Cache navegador)
```

### Linux
```
/tmp                                      (Archivos temporales)
~/.cache                                  (Cache local)
/var/cache/apt/archives                   (Cache de paquetes)
/var/log                                  (Logs antiguos)
```

### macOS
```
/var/tmp                                  (Archivos temporales)
~/Library/Caches                          (Application cache)
~/.Trash                                  (Papelera)
/Library/Localizations                    (Idiomas no usados)
```

---

## 🔐 SEGURIDAD Y RESTRICCIONES

### ✅ SEGUROS (Se pueden borrar automáticamente)
- [ ] Archivos temporales (.tmp, .temp)
- [ ] Cache de navegadores
- [ ] Cache de aplicaciones
- [ ] Logs de más de 90 días
- [ ] Papelera de reciclaje

### ⚠️ REQUIEREN CONFIRMACIÓN (No se borran sin preguntar)
- [ ] Logs del sistema
- [ ] Datos de sesión
- [ ] Archivos de configuración antiguos

### ❌ NUNCA BORRAR (Protegidos)
- [ ] Documentos personales
- [ ] Código fuente
- [ ] Archivos de usuario
- [ ] Bases de datos
- [ ] Archivos de sistema críticos

---

## 📊 MODOS DE OPERACIÓN

### Modo Automático
**Cuándo usar:** Cuando quieres limpiar SIN pensar  
**Qué hace:** Borra solo items seguros (sin preguntar)  
**Tokens gastados:** ~50 líneas pseudocódigo

```
Usuario → "Ejecutar limpieza automática" 
       → Sistema borra items seguros
       → Guarda LOG
       → Muestra: "Se liberaron X MB"
```

### Modo Manual
**Cuándo usar:** Cuando quieres controlar exactamente qué se borra  
**Qué hace:** Muestra lista, tú seleccionas, confirma para items peligrosos  
**Tokens gastados:** ~100 líneas pseudocódigo

```
Usuario → "Modo manual"
       → Sistema muestra lista de items
       → Usuario selecciona (ej: 1,2,4)
       → Sistema pide confirmación para items peligrosos
       → Borra y guarda LOG
```

### Modo Agresivo (v1.1)
**Cuándo usar:** Cuando necesitas liberar MUCHO espacio  
**Qué hace:** Borra TAMBIÉN archivos viejos (>365 días)  
**Tokens gastados:** ~50 líneas pseudocódigo

```
Usuario → "Modo agresivo"
       → Sistema identifica archivos viejos
       → Borra automáticamente
       → Guarda LOG detallado
```

---

## 📝 PAPELERA DE RECUPERACIÓN

Cuando se "borra" un archivo, en realidad se mueve aquí:

```
Windows:  C:\Users\[USER]\AppData\Local\LimpiadorClaude\Papelera\
Linux:    ~/.limpiador_claude/papelera/
macOS:    ~/Library/Application Support/LimpiadorClaude/Papelera/
```

**Estructura de papelera:**

```
Papelera/
├── item_1_20240424_143000/
│   ├── [contenido original]
│   └── metadata.json (cuándo se movió, tamaño, etc)
├── item_2_20240424_143015/
└── ...
```

**Cómo recuperar:** Copias de papelera a ubicación original.

---

## 📋 CRITERIOS DE ÉXITO

### v1.0 (Ahora)
- [ ] Detecta SO correctamente (Windows/Linux/macOS)
- [ ] Modo automático funciona sin errores
- [ ] Modo manual permite seleccionar items
- [ ] Papelera guarda archivos correctamente
- [ ] LOG registra todo (fecha, hora, archivo, tamaño)
- [ ] Interfaz terminal es clara y usable
- [ ] No borra archivos importantes (nunca)
- [ ] Se puede recuperar cualquier archivo de papelera

### v1.1 (Próximo)
- [ ] Modo agresivo detecta archivos viejos (>365 días)
- [ ] Simulación muestra qué se limpiaría sin hacerlo
- [ ] Interfaz gráfica básica funciona

### v2.0 (Futuro)
- [ ] Programación automática cada X días
- [ ] Estadísticas de limpieza (cuánto espacio liberado en total)
- [ ] Exclusiones personalizables

---

## 🐛 CASOS DE PRUEBA

### Test 1: Detección de SO
```
Entrada: Ejecutar programa
Esperado: Detecta automáticamente Windows/Linux/macOS
Éxito: Muestra "Sistema detectado: [SO]"
```

### Test 2: Modo Automático
```
Entrada: Usuario selecciona "Limpieza automática"
Esperado: Se limpian solo items seguros
Éxito: "Se liberaron X MB. Ver LOG para detalles"
```

### Test 3: Papelera de Recuperación
```
Entrada: Usuario quiere recuperar archivo
Esperado: Archivo está en carpeta de papelera
Éxito: Usuario puede copiar de vuelta a ubicación original
```

### Test 4: LOG de Auditoría
```
Entrada: Se ejecuta limpieza
Esperado: LOG contiene: fecha, hora, archivo, tamaño, acción
Éxito: Archivo log.txt existe y está completo
```

---

## 📈 MÉTRICAS DE ÉXITO

| Métrica | Objetivo |
|---------|----------|
| Espacio liberado | 500MB - 5GB (promedio) |
| Tiempo de ejecución | < 30 segundos |
| Archivos incorrectamente borrados | 0 (cero) |
| Tasa de recuperación | 100% (todo recuperable) |
| Compatibilidad de SO | 3/3 (Windows, Linux, macOS) |
| LOG accuracy | 100% (todo registrado) |

---

## 🔄 FLUJO DE TRABAJO

```
Usuario inicia programa
        ↓
Detecta SO automáticamente
        ↓
Muestra menú:
  1. Limpieza automática
  2. Limpieza manual
  3. Ver LOG
  4. Salir
        ↓
[Usuario elige opción]
        ↓
[Opción 1: Automático]
  → Borra items seguros
  → Guarda en papelera
  → Registra en LOG
  → Muestra resumen
        ↓
[Opción 2: Manual]
  → Muestra lista de items
  → Usuario selecciona
  → Confirma para items peligrosos
  → Borra, guarda, registra
  → Muestra resumen
        ↓
[Opción 3: Ver LOG]
  → Abre archivo de auditoría
  → Muestra historial completo
        ↓
¿Más acciones? [Sí → vuelve a menú] [No → Salir]
```

---

## 📚 REFERENCIAS Y DOCUMENTACIÓN

- **Pseudocódigo:** `/pseudocódigos/limpiador_v1.psd`
- **Implementación Python:** `/proyectos/01_limpiador_cache/python_v1.py` (próximamente)
- **Changelog:** Ver `/changelog.md`

---

## ✅ CHECKLIST DE DESARROLLO

### Pseudocódigo (COMPLETO ✓)
- [x] Estructura de datos definida
- [x] Funciones auxiliares implementadas
- [x] Lógica de detección de SO
- [x] Modos automático y manual
- [x] Sistema de papelera
- [x] LOG de auditoría

### Python v1 (PRÓXIMO)
- [ ] Convertir pseudocódigo a Python
- [ ] Pruebas en Windows
- [ ] Pruebas en Linux
- [ ] Pruebas en macOS
- [ ] Documentación de código
- [ ] README de uso

### v1.1 (FUTURO)
- [ ] Modo agresivo
- [ ] Simulación (dry-run)
- [ ] Interfaz gráfica básica

---

## 📞 CONTACTO Y PREGUNTAS

**Desarrollador:** Diego Mercedes Llauger (2026-0048)  
**Institución:** Universidad Dominicano Americana  
**Carrera:** Ingeniería en Ciberseguridad  
**Última actualización:** 2024-04-24

---

**Estado:** En desarrollo | **Versión:** 1.0 | **Completitud:** 50%
