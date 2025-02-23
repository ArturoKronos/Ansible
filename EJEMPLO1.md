# 1: Agregar una tarea cron para ejecutar un script cada día a las 2 AM

***

## Playbook:

```
- name: Agregar una tarea cron
  hosts: servidores
  tasks:
    - name: Crear una tarea cron para ejecutar un script diariamente
      ansible.builtin.cron:
        name: "Backup Diario"
        minute: "0"
        hour: "2"
        job: "/usr/local/bin/backup.sh"
        user: "root"
```

[img](img/img2.png)

### Explicación

`name`: Nombre descriptivo de la tarea cron.

`minute` y `hour`: Definen la hora de ejecución (2:00 AM en este caso).

`job`: Comando o script a ejecutar.

`user`: Usuario que ejecutará la tarea.

### Resultado esperado en el servidor remoto:

```
$ crontab -l -u root
0 2 * * * /usr/local/bin/backup.sh
```

[img](img/img3.png)
