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
 
      
      
 
      
    
 
 
