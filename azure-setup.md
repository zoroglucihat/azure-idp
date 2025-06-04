# Azure Backstage Internal Development Portal Kurulum Rehberi

Bu rehber, Backstage'in Azure servisleri ile entegrasyonu için gerekli adımları açıklar.

## Gerekli Ortam Değişkenleri

Aşağıdaki ortam değişkenlerini tanımlamanız gerekir:

### GitHub Integration (İsteğe bağlı)
```bash
GITHUB_TOKEN=your_github_token_here
```

### Azure DevOps Integration
```bash
AZURE_TOKEN=your_azure_devops_personal_access_token
AZURE_ORG=your_azure_organization_name
```

### Azure AD Authentication
```bash
AZURE_CLIENT_ID=your_azure_app_client_id
AZURE_CLIENT_SECRET=your_azure_app_client_secret
AZURE_TENANT_ID=your_azure_tenant_id
```

### Azure Kubernetes Service (AKS) - İsteğe bağlı
```bash
AZURE_K8S_CLUSTER_URL=https://your-aks-cluster.hcp.eastus.azmk8s.io
AZURE_K8S_TOKEN=your_k8s_service_account_token
AZURE_K8S_DASHBOARD_URL=https://your-aks-cluster-dashboard-url
```

### Backend Secret (Prodüksiyon için)
```bash
BACKEND_SECRET=your_backend_secret_key
```

### Veritabanı Konfigürasyonu (Prodüksiyon için)
```bash
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_USER=backstage
POSTGRES_PASSWORD=your_postgres_password
```

### Azure Resource Management
```bash
AZURE_SUBSCRIPTION_ID=your_azure_subscription_id
AZURE_RESOURCE_GROUP=your_resource_group_name
```

## Azure App Registration Kurulumu

1. Azure Portal'da bir App Registration oluşturun
2. Client ID ve Client Secret alın
3. Redirect URI'yi `http://localhost:7007/api/auth/microsoft/handler/frame` olarak ayarlayın
4. API permissions olarak şunları ekleyin:
   - User.Read
   - Group.Read.All

## Azure DevOps Personal Access Token

1. Azure DevOps'ta Settings > Personal Access Tokens'a gidin
2. Yeni token oluşturun
3. Gerekli izinleri verin:
   - Code (read)
   - Build (read)
   - Release (read)
   - Graph (read)

## Kurulum Adımları

1. Bağımlılıkları yükleyin:
```bash
yarn install
```

2. Ortam değişkenlerini tanımlayın (yukarıdaki listeden)

3. Uygulamayı başlatın:
```bash
yarn start
```

## Özellikler

Bu kurulum ile şu özellikleri kullanabilirsiniz:

- **Azure AD Authentication**: Kurumsal kimlik doğrulama
- **Azure DevOps Integration**: Repository ve pipeline görüntüleme
- **Azure AKS Integration**: Kubernetes cluster yönetimi
- **Azure Sites Integration**: App Service uygulamaları
- **Software Templates**: Azure kaynaklarını otomatik oluşturma

## Troubleshooting

- CORS hataları alıyorsanız, `app-config.yaml`'deki CSP ayarlarını kontrol edin
- Authentication sorunları için Azure App Registration ayarlarını gözden geçirin
- Token'ların geçerli olduğundan ve doğru izinlere sahip olduğundan emin olun 