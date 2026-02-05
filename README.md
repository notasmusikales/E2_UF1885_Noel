# E2 UF1885 - Detección, análisis y resolución de incidencias (ERP-CRM)

**Alumno:** Gonzalez, Noel  
**Fecha:** 2026-02-04  
**Entorno:** Ubuntu Server + Docker  
**Contenedores:** odoo-dev-UF1884 (CRM) | postgres-dev-2 (BD)

---

## 1. Análisis inicial del sistema y parámetros de rendimiento
### 1.1 Servicios de acceso al CRM
- Descripción: 
 - Acceso al ERP/CRM (aplicacion web): contenedor odoo
 - El servicio de base de datos: contenedor postgres-dev-2 (PostgrSQL 16)
 - Servicio de publicación de puerto / acceso web: Docker publica 8069/tcp
 - Red y DNS del sistema: interfaz la IP 192.168.1.130
 - Acceso administrativo remoto: SSH en 22/tcp para tareas de soporte.  
- Evidencias: evidencias/01_analisis/

### 1.2 Parámetros (CPU / RAM / Disco / Red) y relación con CRM+BD
- CPU ~ 97,7 idle, load average: 0.07, 0.05, 0.74
- Conclusiones: No hay saturación de CPU.

- RAM 10Gi total;       1.0Gi usado;       8.7Gi libre
- Conclusiones: Hay suficiente memoria, no hay presión ahora mismo en la RAM.

- Disco: /dev/sda2   tamaño:254G usado: 9.7G  (5%)
- Conclusiones: Hay suficiente espacio de memoria, no hay problemas de almacenamiento.

## 2. Monitorización de procesos y detección de sobrecarga
### 2.1 Proceso problemático detectado
- Proceso/servicio:
 - Contenedor postgres-dev-2 (servicio PostgreSQL para ERP/CRM)
 -Proceso interno forzado por el sistema: yes > /dev/null & (generador de carga del CPU) 
- Datos y justificación:
 - CPU % (postgres-dev-2): 20078%, indica saturación del docker.
 - Consumo de memoria bajo (67.28MiB / 10.6GiB)
 - Saturacion se produce a nivel del CPU.
- Impacto en el CRM:
 - Lentitud extrema en operaciones que dependen de la base de datos.
 - Usuarios perciben bloqueos y esperas prolongadas.
---

## 3. Resolución de una incidencia técnica simulada
### 3.1 Síntomas
### 3.2 Diagnóstico
### 3.3 Acción aplicada
### 3.4 Verificación
### 3.5 Rollback

---

## 4. Simulación de saturación del sistema (CPU o Memoria)
- Técnica utilizada:
- Datos capturados:
- Análisis:
- Verificación requisitos HW/SW:
- Registro:

---

## 5. Documentación y registro técnico
### 5.1 Incidencias detectadas / Acciones / Resultados
### 5.2 Interpretación de documentación en inglés (monitorización / rendimiento / administración CRM)
- Fragmento 1 (EN):
- Interpretación (ES):
- Fragmento 2 (EN):
- Interpretación (ES):
- Fragmento 3 (EN):
- Interpretación (ES):
