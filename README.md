# Домашнее задание к занятию «Управление доступом» - `Мурчин Артем`

### Цель задания

В тестовой среде Kubernetes нужно предоставить ограниченный доступ пользователю.

------

### Чеклист готовности к домашнему заданию

1. Установлено k8s-решение, например MicroK8S.
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключённым github-репозиторием.

------

### Инструменты / дополнительные материалы, которые пригодятся для выполнения задания

1. [Описание](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) RBAC.
2. [Пользователи и авторизация RBAC в Kubernetes](https://habr.com/ru/company/flant/blog/470503/).
3. [RBAC with Kubernetes in Minikube](https://medium.com/@HoussemDellai/rbac-with-kubernetes-in-minikube-4deed658ea7b).

------

### Задание 1. Создайте конфигурацию для подключения пользователя

1. Создайте и подпишите SSL-сертификат для подключения к кластеру.
2. Настройте конфигурационный файл kubectl для подключения.
3. Создайте роли и все необходимые настройки для пользователя.
4. Предусмотрите права пользователя. Пользователь может просматривать логи подов и их конфигурацию (`kubectl logs pod <pod_id>`, `kubectl describe pod <pod_id>`).
5. Предоставьте манифесты и скриншоты и/или вывод необходимых команд.

### Решение 1

Создал и подписал SSL-сертификат для подключения к кластеру:

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-01.png)

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-02.png)

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-03.png)

Настроил конфигурационный файл kubectl для подключения:

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-05.png)

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-04.png)

Манифест Role:

https://github.com/artmur1/22-2.4-K8S/blob/main/files/role.yaml

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-06.png)

Манифест RoleBinding:

https://github.com/artmur1/22-2.4-K8S/blob/main/files/role-binding.yaml

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-07.png)

Роли заданы:

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-08.png)

Проверка роли:

![](https://github.com/artmur1/22-2.4-K8S/blob/main/img/22-2_4-01-09.png)

------

### Правила приёма работы

1. Домашняя работа оформляется в своём Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд `kubectl`, скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.

------

