# Dónde sacar cada entregable – Asignación Capstone DevOps

Guía para localizar y generar cada uno de los 33 entregables de la evaluación (50 puntos, 70% para aprobar).

**Repositorio:** https://github.com/Katapentakill/devops-capstone-project  
**Rama por defecto:** `main`

---

## Tareas 1–2, 7, 21, 22, 29: URLs de GitHub

Estas tareas piden **la URL pública del archivo** en GitHub. Abre el repo, navega al archivo, y copia la URL de la barra del navegador (o clic derecho en "Raw" / "Copy link" según lo que pida la rúbrica).

| Tarea | Puntos | Qué piden | URL que debes enviar |
|-------|--------|-----------|----------------------|
| **1** | 2 | README.md con nombre del proyecto y badge de build actualizado | https://github.com/Katapentakill/devops-capstone-project/blob/main/README.md |
| **2** | 1 | user-story.md (plantilla de historias de usuario) | https://github.com/Katapentakill/devops-capstone-project/blob/main/.github/ISSUE_TEMPLATE/user-story.md |
| **7** | 1 | setup.cfg (nosetests, cobertura, Flake8, Pylint) | https://github.com/Katapentakill/devops-capstone-project/blob/main/setup.cfg |
| **21** | 4 | ci-build.yaml (config YAML, checkout, lint, nosetests) | https://github.com/Katapentakill/devops-capstone-project/blob/main/.github/workflows/ci-build.yaml |
| **22** | 1 | __init__.py con configuración Talisman (encabezados de seguridad) | https://github.com/Katapentakill/devops-capstone-project/blob/main/service/__init__.py |
| **29** | 2 | Dockerfile para construir la imagen | https://github.com/Katapentakill/devops-capstone-project/blob/main/Dockerfile |

**Cómo obtenerlas:** Repo → rama `main` → entra en la carpeta/archivo → copia la URL del navegador.

---

## Tareas 3–6, 8–12, 18, 20, 24, 25, 27, 28, 33: Capturas de pantalla

Todas se sacan del **tablero Kanban de GitHub** del proyecto (Projects), excepto donde se indique otra cosa.

**Dónde está el Kanban:**  
Repo → pestaña **Projects** → tablero con columnas tipo: *New Issues* / *Nuevos Problemas*, *Icebox*, *Product Backlog*, *Sprint Backlog*, *In Progress*, *Review/QA*, *Done* / *Hecho*.

| Tarea | Puntos | Nombre del archivo de captura | Qué debe verse en la captura |
|-------|--------|------------------------------|-----------------------------|
| **3** | 1 | planning-userstories-done.jpeg o .png | Todas las historias de usuario en la columna **Nuevos Problemas** (New Issues). |
| **4** | 1 | planning-productbacklog-done.jpeg o .png | Historias bajo **Icebox** (Ice Box). |
| **5** | 1 | planning-labels-done.jpeg o .png | Product Backlog con historias etiquetadas **Deuda Técnica** o **Mejora** (Labels visibles). |
| **6** | 1 | planning-kanban-done.jpeg o .png | Historias en **Sprint Backlog** con estimación (puntos) y asignadas al **Sprint 1**. |
| **8** | 1 | rest-techdebt-done.png o .jpeg | Historia *"Configurando el entorno de desarrollo"* en columna **Hecho**. |
| **9** | 1 | read-accounts.jpeg o .png | Historia *"Leer una cuenta del servicio"* en **Hecho**. |
| **10** | 1 | list-accounts.png o .jpeg | Historia *"Listar todas las cuentas en el servicio"* en **Hecho**. |
| **11** | 1 | update-accounts.jpeg o .png | Historia *"Actualizar una cuenta en el servicio"* en **Hecho**. |
| **12** | 1 | delete-accounts.jpeg o .png | Historia *"Eliminar una cuenta del servicio"* en **Hecho**. |
| **18** | 1 | sprint2-plan.jpeg o .png | **Dos** historias nuevas en **Sprint Backlog** del **Sprint 2** (p. ej. CI y seguridad). |
| **20** | 1 | ci-kanban-done.jpeg o .png | Historia *"Necesitamos la capacidad de automatizar las verificaciones de integración continua"* en **Hecho**. |
| **24** | 1 | security-kanban-done.jpeg o .png | Historia *"Necesitamos añadir encabezados de seguridad y políticas de CORS"* en **Hecho**. |
| **25** | 1 | sprint3-plan.jpeg o .png | **Tres** historias en **Sprint 3** (p. ej. Docker, Kubernetes, pipeline CD). |
| **27** | 1 | kube-docker-done.jpeg o .png | Historia *"Containeriza tu microservicio usando Docker"* en **Hecho**. |
| **28** | 1 | kube-kubernetes-done.jpg o .png | Historia *"Despliega tu imagen de Docker en Kubernetes"* en **Hecho**. |
| **33** | 1 | cd-pipeline-done.jpeg o .png | Historia *"Crea un pipeline de CD para automatizar el despliegue en Kubernetes"* en **Hecho**. |

**Cómo sacar la captura:** Abre el Project en GitHub, coloca las historias en la columna indicada, haz una captura de pantalla y guarda el archivo con el nombre exacto que pide la tarea.

---

## Tareas 13–17: Archivos con cURL y salida (REST)

Debes tener el **servicio corriendo en local** (o en el lab) y ejecutar los comandos cURL. Guardas el **comando + salida** en un archivo de texto con el nombre indicado; luego **copias y pegas ese contenido** en la respuesta de la tarea.

**Requisito:** Servicio en marcha (`make run` o `honcho start`) y base de datos creada (`flask db-create` o equivalente). Puerto típico: 5000 o 8000 (ajusta la URL si usas otro).

| Tarea | Puntos | Nombre del archivo | Comando de ejemplo (ajusta host/puerto) |
|-------|--------|--------------------|----------------------------------------|
| **13** | 2 | rest-create-done | `curl -i -X POST http://127.0.0.1:5000/accounts -H "Content-Type: application/json" -d "{\"name\":\"Juan\",\"email\":\"juan@ejemplo.com\",\"address\":\"Calle 1\",\"phone_number\":\"+34111\"}"` |
| **14** | 2 | rest-list-done | `curl -i -X GET http://127.0.0.1:5000/accounts` |
| **15** | 2 | rest-read-done | `curl -i -X GET http://127.0.0.1:5000/accounts/1` (usa un id existente) |
| **16** | 2 | rest-update-done | `curl -i -X PUT http://127.0.0.1:5000/accounts/1 -H "Content-Type: application/json" -d "{\"name\":\"Juan Actualizado\",\"email\":\"juan@ejemplo.com\",\"address\":\"Calle 2\",\"phone_number\":\"+34222\"}"` |
| **17** | 2 | rest-delete-done | `curl -i -X DELETE http://127.0.0.1:5000/accounts/1` |

**Dónde sacarlo:** Ejecuta cada comando en la terminal, copia comando + salida completa en un archivo (rest-create-done, rest-list-done, etc.) y pega ese contenido en el formulario de la tarea.

---

## Tarea 19: Salida de GitHub Actions (CI)

| Tarea | Puntos | Nombre del archivo | Dónde sacarlo |
|-------|--------|--------------------|---------------|
| **19** | 2 | ci-workflow-done | **GitHub → repo → pestaña Actions** → elige un *workflow run* del flujo "CI Build" que haya terminado **en éxito** (✓) → clic en el run → ves los jobs y pasos; copia **toda la salida del job** (o de cada step) y guárdala en un archivo llamado `ci-workflow-done`. En la entrega pegas ese texto. Alternativa: con GitHub CLI: `gh run list`, luego `gh run view <id> --log` y guardar en `ci-workflow-done`. |

---

## Tarea 23: Salida de nosetests tras CORS

| Tarea | Puntos | Nombre del archivo | Dónde sacarlo |
|-------|--------|--------------------|---------------|
| **23** | 1 | security-headers-done | En tu máquina o en el lab, con Talisman y CORS ya configurados en `service/__init__.py`, ejecuta: `nosetests -v --with-spec --with-coverage --cover-package=service` (con `DATABASE_URI` configurado si hace falta). Copia **toda la salida del terminal** y guárdala en un archivo llamado `security-headers-done`. En la entrega pegas ese texto. |

---

## Tareas 26, 30, 31: Kubernetes / Docker (lab o entorno con K8s/OpenShift)

| Tarea | Puntos | Nombre del archivo | Dónde sacarlo |
|-------|--------|--------------------|---------------|
| **26** | 1 | kube-app-output | Tras desplegar la app en el cluster (route o port-forward al puerto 8080), abre en el **navegador interno** la URL (ej. http://…:8080 o la ruta de OpenShift). La respuesta suele ser JSON (ej. del endpoint raíz o /accounts). **Copia esa salida JSON** y guárdala en `kube-app-output`. |
| **30** | 2 | kube-images | En la terminal (donde tengas Docker o acceso a la registry): ejecuta `docker images` (o el comando equivalente del lab) para la imagen del microservicio. La salida debe mostrar **Nombre, Etiqueta, ID, Tiempo de creación, Tamaño**. Guarda esa salida en `kube-images`. |
| **31** | 2 | kube-deploy-accounts | En la terminal del lab (con `kubectl` u `oc`): `oc get all -l app=accounts` o `kubectl get deployment,pods,replicaset,service -l app=accounts`. Guarda la salida en `kube-deploy-accounts`. |

---

## Tareas 32 y 33: Pipeline Tekton (CD)

| Tarea | Puntos | Nombre del archivo | Dónde sacarlo |
|-------|--------|--------------------|---------------|
| **32** | 5 | pipelinerun.txt | En la **terminal del lab** (donde esté configurado `tkn` y el pipeline CD): después de ejecutar el pipeline, obtén los logs completos con: `tkn pipelinerun logs -L > pipelinerun.txt` (o el nombre del PipelineRun que corresponda). Copia el **contenido completo** de `pipelinerun.txt` a tu PC y pégalo en la entrega. |
| **33** | 1 | cd-pipeline-done.jpeg o .png | **Kanban de GitHub:** historia *"Crea un pipeline de CD para automatizar el despliegue en Kubernetes"* movida a la columna **Hecho** (después de haber ejecutado el pipeline de CD). Captura de pantalla con ese nombre. |

---

## Resumen rápido por tipo de entregable

- **URLs (copiar en el formulario):** Tareas 1, 2, 7, 21, 22, 29 → desde el repositorio GitHub, archivos en rama `main`.
- **Capturas (.jpeg / .png):** Tareas 3, 4, 5, 6, 8, 9, 10, 11, 12, 18, 20, 24, 25, 27, 28, 33 → tablero Kanban (Projects) del repo.
- **Texto (comando + salida o solo salida):** Tareas 13–17 (cURL), 19 (Actions), 23 (nosetests), 26 (JSON app), 30 (docker images), 31 (get all), 32 (pipelinerun.txt) → terminal / Actions / navegador, guardado en archivos con el nombre indicado; luego copiar/pegar en la entrega.

---

## Checklist antes de enviar

- [ ] README con nombre del proyecto y badge de build en verde (T1).
- [ ] Todas las URLs apuntan a `main` (o la rama que uses) y abren el archivo correcto.
- [ ] Cada captura tiene el **nombre exacto** que pide la tarea (planning-userstories-done, rest-techdebt-done, etc.).
- [ ] Archivos de texto (rest-*-done, ci-workflow-done, security-headers-done, kube-*, pipelinerun.txt) contienen la salida completa que pide la rúbrica.
- [ ] Historias del Kanban están en las columnas correctas (Hecho, Sprint Backlog, etc.) según cada tarea.

Si algo no coincide exactamente con los nombres de la rúbrica (por ejemplo "Nuevos Problemas" vs "New Issues"), usa el nombre que aparezca en tu tablero y el nombre de archivo que exige la tarea.
