# smart_elevator_control_environment
BLM5027 Derin Pekiştirmeli Öğrenme dersi vizesi YL

BLM5027 Derin Pekiştirmeli Öğrenme dersi kapsamında öğrenme algoritmaları ile ortamlar arasında iletişim kurmak için standart bir API olan ve bu API'ye uygun standart bir ortam seti sunarak pekiştirme öğrenme algoritmaları geliştirmek ve karşılaştırmak için açık kaynaklı bir Python kütüphanesi olan OpenAI Gym Taxi-v3 çevresinden yararlanılarak kendi environmentimizi oluşturduğumuz Q-Learning tabanlı akıllı asansör kontrol uygulaması. Standart OpenAI Taxi ortamından farklı olarak özelleştirilmiş 3x1 grid tabanlı çevre (environment) kullanılmıştır. Bu ortamda: Asansör harita üzerinde hareket ederken üç farklı kattan birine yolcuyu indirmekle görevlidir. Her kattaki bekleyen yolcu sayısı gerçekte yoğunluğa bağlı olarak değişkenlik gösterse de, durum uzayının aşırı büyümesini engellemek amacıyla maksimum bekleyen yolcu sayısı asansör kapasitesi ile sınırlandırılmıştır. Bu yaklaşım, modelin çalışabilirliğini artırmak ve öğrenme süresini optimize etmek için uygulanmıştır. Başlangıçta her yolcu için hedef katların tutulduğu bir model tasarlanmıştı. Ancak bu yaklaşım öğrenmeyi zorlaştırmaktaydı. Asansörde bulunan  yolcuların aynı hedef katta indirildiği bir yapı tercih edilmiştir. Bu çalışmada asansör kapasitesi literatürde yaygın olarak kullanılan 600–630 kg (yaklaşık 8 kişi) aralığı referans alınarak belirlenmek istenmiştir. Ancak modelleme sürecinde durum uzayının (state space) boyutu, kullanılan donanımın bellek kapasitesi (RAM) tarafından önemli ölçüde etkilenmektedir. Geliştirme ortamında bellek sınırlarının aşılmaması ve pekiştirmeli öğrenme yöntemlerinin uygulanabilirliğini korumak amacıyla kapasite parametresi 225 kg (yaklaşık 3 kişi) olarak yeniden tanımlanmıştır. Böylece model hem hesaplama açısından yönetilebilir kalmış hem de gerçekçi bir asansör senaryosunu temsil etmeyi sürdürmüştür. Aynı şekilde, binanın kat sayısı da 6 kat olarak tasarlanmak istenirken durum uzayının büyümesini engellemek kat sayısı 3 olarak sınırlandırılmıştır. Bu yaklaşım, modelin çalışabilirliğini artırmak için uygulanmıştır.Q-Learning Yapısı Proje Q-Learning algoritmasını temel alır ve şu özellikleri içerir: Simülasyon sırasında oluşturulan Q-Tablosu, eğitim sonunda dosyaya kaydedilir. Kullanıcı isterse: Eğitim aşamasını atlayarak önceden kaydedilen Q tablosunu yükleyebilir, Böylece taksi doğrudan öğrenilmiş en iyi davranış modeliyle çalışabilir. Eğitim sürecinde: Toplam ödül, kaç denemenin başarısız olduğu, adım sayıları gibi performans metrikleri izlenir ve en iyi model bulunur.

<img width="583" height="455" alt="indir" src="https://github.com/user-attachments/assets/b0da91e4-bf5c-4fcf-9a15-de03c42572d1" />
<img width="571" height="455" alt="indir (1)" src="https://github.com/user-attachments/assets/d4481fca-617d-4513-939b-4b7ad103a4b9" />


Bu not defteri oluşturulurken aşağıdaki kaynaklar kullanılmıştır:

    [1] A Q-learning implementation for OpenAIs Taxi-v3 environment
      https://github.com/woutervanheeswijk/taxi_environment
      
    [2] OpenAI Gym. Taxi-v3 ortamı. OpenAI Gym ortamı MIT Lisansı altında mevcuttur.
      https://github.com/openai/gym/blob/master/gym/envs/toy_text/taxi.py
      
    [3] LearnDataSci. OpenAI Gym ile Python'da Sıfırdan Takviyeli Q-Öğrenme. Taxi-v2 uygulaması.
      https://www.learndatasci.com/tutorials/reinforcement-q-learning-scratch-python-openai-gym/
      
    [4] Botforge. OpenAI Gym render'larını GIF olarak kaydedin. Herkese açık GitHub Gist.
      https://gist.github.com/botforge/64cbb71780e6208172bbf03cd9293553
