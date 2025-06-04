# Azure Internal Development Portal

Bu proje Backstage tabanlı bir Azure internal development portal'dır. Azure servisleri ile entegre edilmiş geliştirici platformu sağlar.

## Özellikler

- 🔐 **Azure AD Authentication**: Kurumsal kimlik doğrulama
- 🏗️ **Azure DevOps Integration**: Repository ve pipeline yönetimi  
- ☁️ **Azure Resource Management**: Azure kaynaklarını görüntüleme ve yönetme
- 🛡️ **Azure AKS Integration**: Kubernetes cluster yönetimi
- 📚 **TechDocs**: Teknik dokümantasyon
- 🔍 **Service Catalog**: Mikro servis katalogu
- 🚀 **Software Templates**: Azure kaynaklarını otomatik oluşturma

## Gereksinimler

- Node.js 20.x (önerilen)
- Yarn 4.x
- Docker (isteğe bağlı, TechDocs için)

## Kurulum

1. Node.js 20 kullandığınızdan emin olun:
```bash
nvm use 20
```

2. Bağımlılıkları yükleyin:
```bash
yarn install
```

3. Azure konfigürasyonu için [azure-setup.md](./azure-setup.md) dosyasını okuyun.

4. Gerekli ortam değişkenlerini tanımlayın (detaylar azure-setup.md'de).

5. Uygulamayı başlatın:
```bash
yarn start
```

Uygulama şu adreslerde çalışacaktır:
- Frontend: http://localhost:3000
- Backend: http://localhost:7007

## Azure Entegrasyonu

Bu portal şu Azure servisleri ile entegre edilmiştir:

### Azure Active Directory
- Kurumsal SSO
- Kullanıcı ve grup yönetimi
- Rol tabanlı erişim kontrolü

### Azure DevOps
- Repository görüntüleme
- Pipeline durumları
- Build ve release bilgileri

### Azure Kubernetes Service (AKS)
- Cluster durumu
- Pod ve deployment bilgileri
- Resource monitoring

### Azure Resource Manager
- Subscription ve resource group'lar
- Resource durumları
- Cost monitoring

## Geliştirme

```bash
# Backend geliştirmesi
yarn workspace backend start

# Frontend geliştirmesi  
yarn workspace app start

# Tüm testleri çalıştır
yarn test:all

# Linting
yarn lint:all
```

## Dağıtım

Prodüksiyon dağıtımı için:

1. Environment değişkenlerini prodüksiyon değerleri ile güncelleyin
2. PostgreSQL veritabanı kurun
3. Docker image'ı build edin:

```bash
yarn build-image
```

4. Azure'da deploy edin (App Service, AKS vs.)

## Katkıda Bulunma

1. Bu repository'yi fork edin
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Değişikliklerinizi commit edin (`git commit -m 'Add amazing feature'`)
4. Branch'inizi push edin (`git push origin feature/amazing-feature`)
5. Pull Request açın

## Lisans

Bu proje MIT lisansı altında lisanslanmıştır.

## Destek

- 📖 [Backstage Dokumentasyonu](https://backstage.io/docs)
- 🚀 [Azure Setup Rehberi](./azure-setup.md)
- 💬 Yardım için: [GitHub Issues](./issues)
