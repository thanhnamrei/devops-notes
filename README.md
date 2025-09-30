devops-notes/
│── README.md                  # Giới thiệu, mục tiêu học DevOps
│── docker/                    # Docker
│   ├── dockerfile.md
│   ├── images-containers.md
│   ├── docker-compose.md
│   └── examples/
│       ├── dotnet-app/
│       └── angular-app/
│── kubernetes/                # Kubernetes
│   ├── pods.md
│   ├── deployments.md
│   ├── services.md
│   ├── ingress.md
│   └── examples/
│       ├── dotnet-k8s.yaml
│       └── angular-k8s.yaml
│── cicd/                      # CI/CD
│   ├── concepts.md
│   ├── github-actions.md
│   ├── gitlab-ci.md
│   ├── jenkins.md
│   └── examples/
│       ├── github-actions-dotnet.yml
│       ├── gitlab-ci-angular.yml
│       └── jenkinsfile
│── monitoring/                # Monitoring & Logging
│   ├── prometheus-grafana.md
│   ├── elk-stack.md
│   └── logging-best-practices.md
└── references.md               # Link tài liệu chính thức & blog


# DevOps Notes

## 🎯 Mục tiêu
- Nắm vững các công cụ cơ bản của DevOps: Docker, Kubernetes, CI/CD
- Biết cách xây dựng pipeline triển khai ứng dụng .NET, Angular
- Làm quen với monitoring và logging

## 📂 Nội dung repo
- **docker/** → Học về containerization, viết Dockerfile, Docker Compose
- **kubernetes/** → Triển khai app trên K8s (Pods, Deployments, Services, Ingress)
- **cicd/** → Thiết kế pipeline (GitHub Actions, GitLab CI, Jenkins)
- **monitoring/** → Quan sát hệ thống với Prometheus, Grafana, ELK

## 🛠 Công cụ
- Docker & Docker Compose
- Kubernetes (minikube, kind, k3s)
- GitHub Actions / GitLab CI / Jenkins
- Prometheus, Grafana, ELK

## 📚 Tài liệu tham khảo
- [Docker Docs](https://docs.docker.com/)
- [Kubernetes Docs](https://kubernetes.io/docs/)
- [GitHub Actions](https://docs.github.com/en/actions)
- [Prometheus](https://prometheus.io/docs/)
