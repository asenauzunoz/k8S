
# **ElasticSearch Nedir?**

Elasticsearch Apache Lucen üzerine geliştirilmiş esnek bir arama motoru yapısıdır. Büyük verileri doğru bir şekilde analiz edip, bu veri blokları içerisinde hızlı bir şekilde full-text arama yapabilmeyi sağlamaktadır. 
 
Tüm text içinde arama yapmak yerine önceden indexlediği veriler üzerinden arama yaparak hızlı bir şekilde sonuca ulaşır.

## *Bu arama işlemi nasıl gerçekleşir?*

- Kaydedilecek veri Apache Lucenn altyapısını kullanarak indexlenir. 

- Bu indexlere ait veriler row olarak tutulur. Arama yapmak istediğimiz veri ilk olarak indexler içerisinde aranır ve sonuç olarak o indexi  içeren veriler listelenir.  

- Elasticsearch cluster yapısına sahiptir ve her node üzerinde çalışır. 

- Loglama,raporlama olarak kullanılabilir. Raporlama ve görselleştirme aracı olan Kibana ile kolayca entegre olabilir.

## *Elasticsearch Avantajları:*
* Java dilinde yazılmış açık kaynak kodlu bir yapıdır. 
* Gerçeğe yakın zamanlıdır. Veriler kaydedildikten saniyeler sonra arama yapılabilir. 
* Dokümanları JSON olarak indexler. 
* Kolay bir şekilde backup yapılabilir. 
* MongoDB, Cassandra, NoSQL ve HBase gibi veritabanlarına doğrudan veri aktarım imkanı vardır. 
* Hızlı ve kolay kullanıma sahiptir. 
* Mapping işlemini veri tipine uygun biçimde gerçekleştirir. 
* Birçok programlama dilini destekler. 

## *ElasticSearch Bileşenleri*
+ **Document**

    Aranılan/indexlenen datanın en küçük birimidir. 

    Elasticsearch document-oriented bir yapıdır. Relational databaselerdeki rowlara karşılık gelirler. 

+ **Type**

    Relational databaselerdeki tablolar olarak düişünebiliriz. 
    Her bir typedaki alanlar mapping olarak adlandırılır. 

+ **Indise**

    Veritabanlarındaki klasik databaseler olarak düşünülebilir. 

    Elasticsearch’ün birden fazla indice’i olabilir. Indicelerin ayarları kendine özgüdür.

+ **Cluster**

    Birden fazla node var ve bu nodelar kendi içinde haberleşebiliyorsa bu kümeye cluster denir.

    Bir data partionları ayrı nodelara dağıtılarak cluster yapısı oluşturulabilir. Bu da performansı artıcı bir yaklaşım olabilir.

+ **Shard**

    Bir data yatayda parçalara bölünüyorsa bu parçaların her birine shard diyoruz.

    Tek seferde tüm veriyi indexlemek yerine parçalara ayırıp farklı nodelar üzerinde paralel bir yapı oluşturarak performansın arttırılması hedeflenebilir.

+ **Replica**

    Shardların devre dış kalma ihtimaline karşı birden fazla kopyasını oluşturmasını sağlayarak veri kaybını önlemeyi amaçlar.

    Bir shardın kopyası başka bir node üzerinde olmalıdır ki node çöktüğünde diğer node üzerinden veri kaybının önlenebilmesi sağlanabilsin. 