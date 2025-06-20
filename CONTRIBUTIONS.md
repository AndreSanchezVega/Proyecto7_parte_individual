# Contribuciones de André Sánchez Vega

## Sprint 1
- **2025-06-12**: Creé `scripts/simulate_drift.sh` para forzar un drift y registrar el resultado de `terraform plan` en `logs/drift_<timestamp>.log`.  
  Commit: [feat(script): (Issue #6) crear simulate_drift.sh para forzar drift](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/13/commits/fc0a5a1b39b5e89664bd7c52be9f96f50e0e4ac9)  
  Pull request grupal: [#6](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/13)

- **2025-06-12**: Añadí el esqueleto de `balanceador/balanceador.py` (definición de funciones y estructura básica, sin lógica de procesamiento).  
  Commit: [feat(balanceador): (Issue #7) agregar esqueleto sin lógica del balanceador](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/13/commits/b8c6855c07f92174121cf47ae41eb8c7fbb508a6)  
  Pull request grupal: [#7](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/13v)

## Sprint 2
- **2025-06-18**: Añadí `balanceador/settings.json` con la clave `"delay"` para configurar el retardo del daemon.  
  Commit: [chore: añadir settings.json con parámetro delay](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/34/commits/8d9db4cd427f67ba042920175434f0e928c78b4e)  
  Pull request grupal: [#21](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/34)

- **2025-06-18**: Desarrollé `scripts/simulate_requests.sh` para generar 10 archivos `req_<n>.txt` con el texto “petición <n>” en `balanceador/incoming_requests/`.  
  Commit: [feat(script): (Issue #20) añadir simulate_requests.sh para generar archivos dummy](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/34/commits/1b1097a6ff39dbac055ad6fd24f0966484f3a740)  
  Pull request grupal: [#20](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/34)

- **2025-06-18**: Convertí `balanceador/balanceador.py` en daemon, leyendo el `delay` de `settings.json`.  
  Commit: [feat(balanceador): (Issue #21) ejecutar balanceador en modo daemon con delay configurable](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/34/commits/510aa7634bf0d883645aa6debc08d1231b689263)  
  Pull request grupal: [#21](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/34)

## Sprint 3
- **2025-06-19**: Creé `scripts/cost_saving.sh` que apaga/enciende `service_3/` según horario (00:00–06:00 / 06:01–23:59) y registra cada evento en `balanceador/logs/cost.log`.  
  Commit: [feat(script): (Issue #29) agregar script cost_saving.sh para apagar/encender service_3](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/38/commits/e009dba7c34981a72eb313c688244a26a0e9e703) 
  Pull request grupal: [#29](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/38)

- **2025-06-19**: Integré `cost_saving.sh` en `balanceador/balanceador.py` usando `subprocess.run`, invocándolo antes de cada ciclo de balanceo.  
  Commit: [feat(balanceador): (Issue #30) integrar cost_saving.sh como subproceso](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/38/commits/17d7337e29817b5a75fe1ed7911a7294c62153ca)  
  Pull request grupal: [#30](https://github.com/Grupo-9-CC3S2/Proyecto-7/pull/38)
