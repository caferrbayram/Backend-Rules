# İyi Yapılandırılmış Kod ve Proje Dizini

- **Proje Yapısı**: Projeler, modüler ve katmanlı bir yapıya sahip olmalıdır. Tipik olarak, Controller, Service, Repository gibi katmanlar arasında net bir ayırım yapılmalıdır. Bu sayede, her katman kendi sorumluluğunu taşır ve başka bir katmanın işlevlerine müdahale etmeden geliştirme yapılabilir.

- **Klasör Yapısı**: Kodun düzenli olması için proje içinde tutarlı bir klasör yapısı oluşturulmalıdır. Örneğin:
      
      src/
        ├── main/
            ├── java/
                ├── com/
                    ├── example/
                        ├── controller/
                        ├── service/
                        ├── repository/
                        ├── model/
                        ├── exception/
            ├── resources/
                ├── application.properties