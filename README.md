# MES Infrastructure

Enterprise Ansible infrastructure project for MES services.

## Current target

### Telemetry VM
- MQTT: 9000
- MQTT fallback: 9001
- Socket tunnel: 5000
- FINS: 9600
- GVCP: 3956
- MES Backend API: TBD (9000 conflicts with MQTT and must be finalized)

### Database VM
- MongoDB: 7017 (verify this is intentional; MongoDB commonly uses 27017)
- PostgreSQL: 5432
- Grafana: 3000

## Architecture

Git -> Semaphore -> Ansible -> Linux VMs

Terraform will be integrated later to provision the VMs in Proxmox.

## First implementation goal

1. Configure Semaphore repository.
2. Add SSH credentials.
3. Add development inventory.
4. Test Ansible connectivity to the manually-created Linux VMs.
5. Build common configuration.
6. Add service roles one by one.
