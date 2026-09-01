                         ┌──────────────┐
                         │   Developer  │
                         └──────┬───────┘
                                │
                           git push
                                │
                                ▼
                       ┌─────────────────┐
                       │     GitHub      │
                       │                 │
                       │ Dockerfile      │
                       │ index.html      │
                       │ buildspec.yml   │
                       └────────┬────────┘
                                │
                           Webhook
                                │
                                ▼
                       ┌─────────────────┐
                       │  CodePipeline   │
                       │                 │
                       │ Source          │
                       │ Build           │
                       │ Deploy          │
                       └────────┬────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │    CodeBuild    │
                       │                 │
                       │ Docker Build    │
                       │ Docker Tag      │
                       │ Docker Push     │
                       └────────┬────────┘
                                │
                           Push Image
                                │
                                ▼
                       ┌─────────────────┐
                       │      ECR        │
                       │ Docker Registry │
                       └────────┬────────┘
                                │
                           Pull Image
                                │
                                ▼
                       ┌─────────────────┐
                       │ ECS Fargate     │
                       │                 │
                       │ ┌─────────────┐ │
                       │ │ Task 1      │ │
                       │ │ Container   │ │
                       │ └─────────────┘ │
                       │                 │
                       │ ┌─────────────┐ │
                       │ │ Task 2      │ │
                       │ │ Container   │ │
                       │ └─────────────┘ │
                       └────────┬────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │       ALB       │
                       └────────┬────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │   CloudFront    │
                       └────────┬────────┘
                                │
                                ▼
                            INTERNET
                                │
                                ▼
                              Users
