# Proyecto 7: Operaciones y recuperación ante desastres locales para infraestructura Terraform

**Nombre:** Andre Alvaro Sanchez Vega  
**Correo institucional:** andre.sanchez.v@uni.pe  

**Título del proyecto grupal:**  
Operaciones y recuperación ante desastres locales para infraestructura Terraform  

**URL del repositorio grupal:**  
https://github.com/Grupo-9-CC3S2/Proyecto-7

---

## Mi rol y contribuciones

Me encargué principalmente de:
- **Simulación de desviaciones (Sprint 1):**  
  - Creación del script `scripts/simulate_drift.sh` para forzar un cambio en `iac/main.tf` (renombrando el recurso `service_1` a `service_1_drift`), ejecutar `terraform init -input=false && terraform plan` y registrar la salida en `logs/drift_<timestamp>.log`.  
  - Desarrollo del esqueleto `balanceador/balanceador.py` (función `main()` vacía con comentarios `# TODO` para las futuras `distribute()` y `health_check()`), y creación de la estructura de carpetas vacías:
    ```
    balanceador/
    ├─ incoming_requests/
    ├─ service_1/
    ├─ service_2/
    └─ service_3/
    ```
- **Simulación de alta disponibilidad (Sprint 2):**  
  - Creación del script `simulate_requests.sh` para generar peticiones dummy.  
  - Adaptación de `balanceador.py` para ejecutarse en modo daemon con delay configurable.

- **Simulación de gestión de costos (Sprint 3):**  
  - Desarrollo del script `cost_saving.sh` que apaga/enciende `service_3/` según la hora (00:00–06:00 y 06:01–23:59).  
  - Integración de ese script en `balanceador.py` usando `subprocess.run`, registrando cada evento en `balanceador/logs/cost.log`.


## Instrucciones para clonar y probar

```bash
git clone https://github.com/tu_usuario/proyecto7-andre_sanchez_vega.git
cd proyecto7-andre_sanchez_vega


python3 -m venv .venv
source .venv/bin/activate

# — Sprint 1: forzar y registrar drift
chmod +x scripts/simulate_drift.sh
bash scripts/simulate_drift.sh

# — Sprint 2: generar peticiones dummy
chmod +x scripts/simulate_requests.sh
bash scripts/simulate_requests.sh

# — Sprint 3: ahorro de costos
chmod +x scripts/cost_saving.sh
bash scripts/cost_saving.sh

# — Ejecutar balanceador en background
chmod +x balanceador/balanceador.py
nohup py balanceador/balanceador.py > balanceador/logs/daemon.log 2>&1 &
```
