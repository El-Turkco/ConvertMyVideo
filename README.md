# ConvertMyVideo
Convert My Video XTF çözümü

İlk olarak Nmap aracı ile bir tarama gerçekleştiriyoruz.
![NmapScann](https://user-images.githubusercontent.com/103064152/221641032-59ab26a5-90ac-4ec9-a12e-d2c6233d1fa8.png)

Daha sonra 80 portuna yani Web sayfasına gidiyoruz.

![web page](https://user-images.githubusercontent.com/103064152/221641285-e77a3d84-a134-4f65-9c57-b892d6bbf8c5.png)


Burdaki input kısmında birşeyler denedim ancak birşey bulamadım.Daha sonra kaynak kodlarına baktım.

![main js](https://user-images.githubusercontent.com/103064152/221641538-6c68c923-0462-4ffd-87d6-315f671351d2.png)

Daha "Burp Suite" aracını kullanarak istekleri yakaldım.Requets kısmındaki bir tane parametreyi değiştirip "code injection" açığı olduğunu tespit ettim.

![id](https://user-images.githubusercontent.com/103064152/221642054-59788933-2929-4871-9650-7616c1e21e90.png)

Reverse shell kodunu kendi makinemi kaydettim.Daha sonra "wget" aracını kullanarak yazdığım shell dosyasını web sitesine yükledim.

![reverse_shell](https://user-images.githubusercontent.com/103064152/221642800-ae6345d9-bab0-4601-8177-81cb43106152.png)

Daha sonra dinleyici açarak Shell aldım.
![listener](https://user-images.githubusercontent.com/103064152/221643417-0ff162dc-a768-4f78-8c2f-e3b3b4930225.png)

![shell](https://user-images.githubusercontent.com/103064152/221643353-33c6e957-6ef1-4d2d-8191-b75a04d51cc0.png)

"cat flag.txt" komutunu kullanarak flag aldım.

"find / -perm -4000 2> /dev/null" komutu ile SUID baktım. "echo" komutunu kullanıp /tmp/clean.sh dosyasını "root" hakkları ile açabiliyordum.

"echo "cat /root/root.txt > rootoldum.txt" >> clean.sh" komutu ile clean.sh dosyası okudumda root falg aldım.


