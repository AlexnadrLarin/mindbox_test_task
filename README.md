# mindbox_test_task

## Описание

Тестовое задание Mindbox для SRE.  
Выполнил Ларин Александр. \
Ссылка на резюме: https://hh.ru/resume/7a00cf9fff0f580d120039ed1f77564b714842

Пример деплоймента веб-приложения в Kubernetes с автоскейлингом и минимальной отказоустойчивостью.

Используется:
- **Deployment** — управляет подами
- **Service** — доступ к приложению внутри кластера
- **HPA** — автоматическое масштабирование по CPU
- **PDB** — защита подов при эвакуации нод

---

## Файлы

- `deployment-local.yaml` — для локального кластера (без topologySpreadConstraints)  
- `deployment-cloud.yaml` — для облачного кластера (с topologySpreadConstraints)  
- `hpa.yaml` — автоскейлинг по CPU  
- `pdb-cloud.yaml` — PodDisruptionBudget для облачного кластера (локальный запускается с 1 репликой)

---

## Запуск

Применяем деплоймент:

Для локального кластера:
```bash
kubectl apply -f deployment-local.yaml
