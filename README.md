# K8s
![kind](https://user-images.githubusercontent.com/78857072/206575533-e267a09b-5754-4809-90cd-b2e4b2f1ef4c.png)

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
   
 ### *scheduler*
   Yeni oluşturulan, henüz node ataması yapılmamış podları kontrol eder ve hangi node üzerinde çalışacaklarını belirler.
   
 ### *container runtime*
   Containerları çalıştırmaktan sorumludur. Docker, containerd, CRI-O.
   
 ### *kubelet*
   Pod içerisinde tanımlanmış containerların çalışmasından sorumludur. Containerların çalışır durumda ve sağlıklı olmasını sağlar.
   
 ### *kube-proxy*
   Podların ağ kurallarını ve TCP,UDP,SCTP trafik akışlarını yönetir. 
 # **KS8 KURULUMU**
 
 ## Minikube
 
      minikube start
      //Virtual machine managers: Hyper-V, Docker, Hyperkit, KVM, Parallels, Podman, VirtualBox, Vmvare
      minikube start --drive=hyperv  
 #### Minikube status
      minikube status
 ####  80 portunda basit bir deployment
      kubectl create deployment hello-minikube --image=kicbase/echo-server:1.0
      kubectl expose deployment hello-minikube --type=NodePort --port=8080
      kubectl get services hello-minikube
      minikube service hello-minikube
 #### Minikube cluster
      minikube pause
      minikube unpause
      minikube stop
      //default memory limitini değiştirmece
      minikube config set memory 9001
      minikube addons list
      minikube start -p aged --kubernetes-version=v1.16.1
      minikube delete --all
      
  ## Install for macOS
  
  #### Son sürüm için:
  
      curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/amd64/kubectl.sha256”
      
  #### Belirli bir sürüm indirilecekse eğer: -> ..release/$(istenilen sürüm linki) 
  exp:
     
      curl -LO "https://dl.k8s.io/release/v1.26.0/bin/darwin/amd64/kubectl"
      
  #### .kubectl dosyasının çalıştırılabilir olması için yetki 

      chmod +x ./kubectl
      
  #### .kubectl dosyasını local sistem pathine taşıyoruz
  
  NOTE: /usr/local/bin dosya yolunun olduğundan emin olalım.
     
     sudo mv ./kubectl /usr/local/bin/kubectl
     sudo chown root: /usr/local/bin/kubectl
     
  #### Yüklenen sürümün güncelliğinden kontrol
  
     kubectl version --client
  
  #### Daha detaylı versiyon çıktısı için
  
      kubectl version --client --output=yaml
      
:exclamation: zsh: bad CPU type in executable: kubectl -> bu şekilde bir hata ile karşılaşılırsa eğer:

:high_brightness: macOS, Apple silikon için üretilmemiş bir uygulamayı çalıştırmayı denediğinde, uygulamayı otomatik olarak Apple silikona çevirmek için Rosetta 2'yi yüklemenizi ister. Terminal'de, eski mimari komut satırı araçlarını çalıştırmak için eksik Rosetta için otomatik algılama yoktur.
  
      softwareupdate --install-rosetta
  
    
 
      
    
 
 
