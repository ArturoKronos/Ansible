# 2: Eliminar una tarea cron existente

## Playbook:
```
- name: Eliminar una tarea cron
  hosts: all
  tasks:
    - name: Remover la tarea cron de backup
      ansible.builtin.cron:
        name: "Backup Diario"
        state: absent
        user: "root"
```
