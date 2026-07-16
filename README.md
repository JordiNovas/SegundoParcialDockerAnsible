# Laboratorio de Ansible con Docker

## Objetivo

Automatizar tareas administrativas utilizando Ansible sobre contenedores Docker con Ubuntu.

---

## Archivos del proyecto

```
ansible-lab/
├── docker-compose.yml
├── inventory.ini
├── playbook.yml
└── README.md
```

---

## Levantar los contenedores

```bash
docker compose up -d
```

Verificar:

```bash
docker ps
```

---

## Instalar Python

Servidor 1

```bash
docker exec -it server1 bash

apt update
apt install -y python3
exit
```

Servidor 2

```bash
docker exec -it server2 bash

apt update
apt install -y python3
exit
```

---

## Verificar conectividad

```bash
ansible docker -i inventory.ini -m ping
```

---

## Ejecutar el Playbook

```bash
ansible-playbook -i inventory.ini playbook.yml
```

---

## Resultado esperado

El playbook realiza las siguientes tareas:

- Muestra el nombre del host.
- Muestra el sistema operativo.
- Crea el directorio `/tmp/ansible-demo`.
- Crea el archivo `info.txt`.
- Escribe información del servidor.
- Crea los directorios:
  - logs
  - backup
  - config
- Muestra un mensaje cuando el sistema operativo es Ubuntu.

---

## Captura de pantalla

Agregar aquí una captura de la ejecución exitosa del playbook.

```
(ansible-playbook ejecutado correctamente)
```