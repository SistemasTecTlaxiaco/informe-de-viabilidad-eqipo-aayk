# 🛡️ El Escudo Anti-Riesgo — Proyecto Stellar Demo

## 🌐 Contexto

Este documento presenta la **matriz de riesgos** aplicada a un proyecto de ejemplo desarrollado con **Stellar y Soroban**, orientado a la creación de una aplicación descentralizada que gestione transacciones seguras y transparentes.  
El objetivo es anticipar, evaluar y mitigar los principales riesgos técnicos, operativos y sociales durante el ciclo de vida del proyecto.

---

## ⚔️ Fase 1: Identificación de Riesgos

| Nº | Riesgo | Tipo |
|----|---------|------|
| 1 | Falla en la integración con la red Stellar o Soroban | Técnico |
| 2 | Pérdida o exposición de claves privadas | Seguridad |
| 3 | Retrasos en el cronograma de desarrollo | Operativo |
| 4 | Baja adopción o confianza de usuarios | Social |
| 5 | Cambios en las políticas o actualizaciones de Stellar | Externo |

---

## 📊 Fase 2: Evaluación de Impacto

| Riesgo | Impacto | Probabilidad | Nivel de Amenaza |
|---------|----------|---------------|------------------|
| Falla en la integración con Stellar o Soroban | Alto | Medio | **Crítico** |
| Pérdida de claves privadas | Alto | Bajo | **Crítico** |
| Retrasos en el desarrollo | Medio | Alto | **Alto** |
| Baja adopción ciudadana | Medio | Medio | **Moderado** |
| Cambios en políticas de Stellar | Alto | Bajo | **Moderado** |

---

## 🧠 Fase 3: El Diseño del “Escudo de Defensa”

| Riesgo | Estrategia | Descripción de Acción |
|--------|-------------|-----------------------|
| Falla en la integración con Stellar | **Mitigar** | Usar el SDK oficial de Stellar y Soroban; implementar pruebas unitarias y CI/CD. |
| Pérdida de claves privadas | **Evitar** | Utilizar cifrado AES local, variables de entorno y secretos en GitHub Actions. |
| Retrasos en el desarrollo | **Mitigar** | Crear cronograma ágil (Scrum) con revisiones cada 3 días. |
| Baja adopción ciudadana | **Aceptar/Mitigar** | Realizar campañas informativas y pruebas piloto con usuarios. |
| Cambios en políticas de Stellar | **Transferir** | Ajustar versiones y apoyarse en la comunidad Stellar para soporte. |

---

## 💻 Fase 4: El Refugio del Código (Pruebas y Resiliencia Técnica)

| Subactividad | Descripción |
|---------------|-------------|
| 4.1 Prueba de Ataque Simulado | Simular fallos de conexión con Stellar y errores en Soroban para validar reconexión automática. |
| 4.2 Validación del Escudo | Registrar resultados de las pruebas en la rama `risk-tests` del repositorio. |
| 4.3 Informe de Resiliencia | Documentar qué riesgos fueron mitigados y cuáles siguen activos. |

### 🧩 Ejemplo de Prueba en Python (SDK Stellar)

```python
from stellar_sdk import Server, Keypair

try:
    server = Server("https://horizon-testnet.stellar.org")
    keypair = Keypair.random()
    account = server.load_account(keypair.public_key)
    print("Conexión exitosa:", account)
except Exception as e:
    print("Error de conexión con Stellar:", e)
