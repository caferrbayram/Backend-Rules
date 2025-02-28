# Kodun Yinelemelerden Kaçınması ve Soyutlama

- **DRY (Don't Repeat Yourself)**: Aynı kodu tekrarlamaktan kaçınılmalı ve tekrar eden kod parçaları için yardımcı metodlar veya ortak sınıflar oluşturulmalıdır. Bu, ko    bakımını    kolaylaştırır ve hata yapma olasılığını azaltır. Örneğin, birden fazla repository'den veri çekerken aynı findById işlemi tekrarlanabilir. Bunun yerine, ortak   metod ile bu işlemi  soyutlayarak kodu daha temiz ve sürdürülebilir hale getirebilirsiniz.
      
      Yanlış:
    
      userRepository.findById(userId).orElseThrow(() -> new RuntimeException("User not found"));
      orderRepository.findById(orderId).orElseThrow(() -> new RuntimeException("Order not found"));
      
    
      Doğru:
    
      private <T> T findEntityById(JpaRepository<T, Long> repository, Long id, String entityName) {
          return repository.findById(id).orElseThrow(() -> new RuntimeException(entityName + " not found"));
      }
      
    
- **Soyutlama ve Tekrar Kullanılabilir Yapılar**: Proje geliştikçe, tekrar eden işlemleri merkezi bir yapıda toplayarak modüler ve sürdürülebilir bir kod yapısı oluştur    önemlidir.  Soyutlama ve genel yapı kullanarak, farklı API’lere yönelik işlemleri merkezi bir sınıfta tanımlayarak tekrar eden kodlardan kaçınılabilir. Örneğin, bir REST cli   yapısı, tüm HTTP    işlemlerini (GET, POST, PUT, DELETE) soyut bir sınıfta tanımlayarak farklı API client sınıflarında bu işlemleri tekrar etmektense, yalnızca API’ye ö   işlemleri yazabiliriz.
    
      Avantajlar:
      - Tekrar Kullanılabilirlik (DRY): Ortak işlemler bir sınıfta tanımlanarak, farklı sınıflarda tekrar edilmesi engellenir.
      - Modülerlik: Kodun farklı bölümleri birbirinden bağımsız çalışabilir, bu da genişletme ve bakım kolaylığı sağlar.
      - Test Edilebilirlik: Soyut sınıflar sayesinde bağımlılıklar dışarıdan geçilebilir, bu da test yazmayı kolaylaştırır.
      - Hata Yönetimi: Ortak hatalar merkezi bir yerde yönetilerek, farklı bölümler için tek tip hata işleme sağlanır.
    
    Bu yaklaşım, projede farklı işlemler için de uygulanabilir (örneğin, veri doğrulama, servis katmanı işlemleri, vs.).