# Lesson 7: EKS Cluster Deployment

Цей проєкт містить конфігурацію Terraform для розгортання інфраструктури в AWS та Helm-чарт для Django-застосунку.

## Опис модулів
* **VPC**: Створює мережу з публічними та приватними підмережами у 3 зонах доступності.
* **ECR**: Репозиторій для Docker-образів із активованим скануванням при пуші.
* **EKS**: Кластер Kubernetes та Node Group (t3.medium) для роботи застосунку.
* **S3-backend**: Налаштування віддаленого зберігання стейту (закоментовано в backend.tf).

## Команди для керування
1. **Інфраструктура**:
   `terraform init` -> `terraform plan` -> `terraform apply`
2. **Оновлення доступу до кластера**:
   `aws eks update-kubeconfig --region us-west-2 --name lesson-7-eks-cluster`
3. **Деплой через Helm**:
   `helm install django-app ./charts/django-app`