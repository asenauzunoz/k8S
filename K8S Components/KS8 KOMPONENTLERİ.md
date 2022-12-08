# **KS8 KOMPONENTLERİ**

- apiserver(APi)
- etcd (veri deposu)
- controller-manager
- scheduler

 ### *apiserver(APi)*

   Tüm komponent ve nodeların direkt olarak iletişim kurabildiği tek komponenttir.

 ### *etcd (veri deposu)*

   Cluster, metadata ve diğer tüm objelerin bilgilerinin tutulduğu veri deposudur.

 ### *controller-manager*

   desired state = current state prosesini işler. Apiserver ile etcd'de bulunan cluster durumunu incleyerek varsa bu farkı oluşturan kaynakları oluşturur Gerekirse siler, günceller, oluşturur ve durumu eşitler.

