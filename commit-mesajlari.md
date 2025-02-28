# Commit Mesajları

- **Format**: Commit mesajları şu formatta olmalıdır:

    - **Yapılan İşin Madde Numarası**: Yapılan işin hangi trello kartına veya jira maddesine ait olduğunu belirtir.
    - **Kısa Başlık**: Yapılan değişikliğin özetini içerir.
    - **Detaylı Açıklama (Opsiyonel)**: Yapılan değişikliğin detaylarını maddeler halinde açıklayabilir.
    - **İşlevsel Commitler**: Commit mesajları, yapılan değişikliğin türünü ve amacını belirten anahtar kelimelerle (feat, fix, refactor, etc.) başlamalıdır.
    - **Commit örneği** ;

        AVL-1234 - Implement email notification service

        - Added support for sending emails on user registration.  
        - Configured SMTP settings via application properties.  
        - Included unit tests for email service functionality.  