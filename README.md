# III.hafta-odevleri


####  1)  .Net kodu nedir ve nasıl derlenir?

   -   .NET  çatısı farklı dillerin aynı ortamda çalışmasını sağlar.
   -   Projenin bir bölümü VB.NET diğer bölümü C# ile kodlanmışlabilir. .NET  barındırdığı ortak dil çalışma zamanı (Common Language Runtime) sayesinde, .NET in deslektediği diler ile yazılmış kodları makine diline çevirerek.Yazılımlarda çoklu dil kullanmaya olanak sağlar.
   -  MSIL(Microsoft Intermediate Language) to native compiler : MSIL kodu makine diline çevirir.
   -  Code Menager: Kodu uygulayarak kontrol eder.
   -  Garbage Collector : Objelerin yaşam sürelerini otomatik olarak denetler.
   -  NET Framework Class Libary Support: Kodda yer alan classları .NET Framework ile birleşirir.
   -  Her kod öncelikle kendine ait derleyicisinde derlenir. Mesela Visual J# ile yazılmış kod önce Visual J# derleyicisinde derlenir. Kendi derleyicisinde derlenen kod MSIL (Microsoft Intermediate Language) ye göre yeniden derlenir. Elde ettiğimiz MSIL kodu kendi başına çalıştırılabilir bir kod değildir. MSIL birtakım özel taşınabilir assembly koddan oluşur. Program çalıştırıldığında MSIL olarak derlenmiş kodu çalıştırılabilir bir kod haline CLR getirir. Bu işlem tüm .NET dilleri için aynı şekilde uygulandığı için .NET dilleri arasında performans farkı yok denecek kadar azdır. Bu yok sayılabilecek farkta dillerin kendi derleyicilerinin performans farklarından doğabilir.
        - Derleme Süreci
          - C# Kodu -> C# Derleyicisi -> MSIL Derleyicisi -> (Taşınabilir Assembly kod) MSIL Kod
        - Çalıştırma Süreci
          - MSIL Kod -> CLR(Common Language Runtime) -> Makine Dil
   
####  2)  Roslyn compiler ne işe yarar?

  - Roslyn compiler c# ve basic dillerini analiz ederek bir managed kütüphane oluşturması için tasarlanmıştır.(karmaşıklığı gidermek amacıyla)
  - Tabi ki böylesi büyük bir managed kütüphane oluşturulmuşken bunu scripting gibi uygulamalara esneklik kazandıracak farklı yönlerde kullanmak istenilmesi oldukça mantıklı. Dili bir derleyici gibi görüyor olmanın verdiği güçle daha iyi analiz ve refactor  yapabilir, kendi alanımıza özgü dilimizi (Domain Specific Language, DSL) geliştirebilir ya da kendi kendine öğrenen, hatalardan ders çıkaran uygulamalar geliştirebiliriz.
  - Zengin kod analizi API'leri ile açık kaynaklı C # ve Visual Basic derleyicileri sağlar. Visual Studio tarafından kullanılan aynı API'lerle kod analizi araçları oluşturmaya olanak tanır.
  
####  3)  Restful servisler nasıl çalışır? Alternatifleri nelerdir ve nasıl çalışırlar?

  - HTTP protolü üzerinden çalışırlar.
  - Sunucu-istemci arasındaki veri iletişim yoludur.
  - Stateless(durumsuzdur) Yani o anki kullanıcı durumu yada geçmişinden habersizdir.
  - istemci-sunucu arasında taşınan verilerde ekstra başlık bilgileri saklanmaz, istemciye ait detaylar bulunmaz, bu bilgiler istemci-sunucu arasında taşınmaz.
  - Esnek bir yapıya sahiptir.
  - JSON,XML,TEXT dosyalarıyla veri alışverişi yapılmasını sağlar.
  - JSON ile aynı veriyi çok daha küçük boyutla taşıyabilir.
  
    - Alternatifi olan SOAP ;
      
      - Soap veri formatı olarak xml kullanılır buda veri boyutunu oldukça yüksek tutar.
      - Belirli bir kurala göre yazılmalıdır.
      - Envelope, servis istek ve cevaplarının bilgilerini içerir. XML Root elemanı zorunluluktur. İçeriğinde Hader, Body ve Fault alanlarını barındırır.
      - Header, meta-data gibi bilgiler iletmeye yarar.
      - Body, istekte ve cevapta mesaj adı ve parametreleri barındırır.
      - Fault, istek sonucu bir hata var ise hata mesajını / durumu içerir.
    -  Alternatifi olan gRPC ;
    
          -  Yazılım dili bağımsız.
          -  Yüksek perfomansa sahip
          -  Açık kaynak kodlu 
####  4)  Extension method nedir? Nasıl yazılır?

  - Genişletme metodları olarak bilinirler.
  - Extension metodlar herhangi bir yeni nesne oluşturmadan, üzerinde işlem yaptığınız nesne üzerinden çağrılabilen "genişletilmiş" manasına gelen çok pratik               metodlardır.
  - Bu metodları kullanarak hem extra iş yükünden kurtulmuş olursunuz, hem de sürekli aynı kodları yazmak zorunda kalmazsınız.
  - Public static bir sınıf oluşturulur.
  - Yapmak istediğimiz işlemleri gerçekleştiricek metod yazılır.
  - Metod genişleme metoduna dönüştürülür.
      - Nasıl Yazılır?  
        - public **static** class Extensions
        -  {
        -   public **static** string GetFirstThreeCharacters(**this** String str)
        -    {
        -      if(str.Length < 3)
        -     {
        -       return str;
        -     }
        -        else
        -      {
        -       return str.Substring(0,3);
        -      }
        -    }
        -  }
####  5)  MVC'nin alternatifleri nelerdir?

  - Asp.net Core
  - Go
  - FastAPI
  - PhP
  - koa
  - Ruby on Rails
  - Flask
  - Express.js
  - Yii
  - Symfony
  - Django
  - Laravel 5
  - Haxe
  - Clojure
  - Nim
  - CakePHP
  - Spring MVC
  
####  6)  Architectural pattern nedir? Neden ihtiyaç duyuyoruz?

  - Oluşturulacak olan bir yazılımın mimarisini(oluşumunu,gelişimini) ele alınan ön hazırlıktır.
  - Yazılımımızda hangi teknolojiyi kullanacağımız nasıl kullanmamız gerektiği hangi araçlara yer vermemiz gerektiğini belirlememizde bize faydası olan mimari kavramdır.
  - Oluşturulan mimari sayesinde projenin gelişimi oldukça hızlı testleri oldukça hızlı ve geri dönüş süreleri ve çözümleri daha başarılı hale gelmektedir.
 -  Neden ihtiyaç duyuyoruz ? İhtiyaçlarımız doğrultusunda doğru şeyleri doğru işleri yapabilmek için. Hakkı hocamızında dediği gibi bir binanızın temelini iki katlı olacak şekilde planlayıp üzerine altı kat çıkmamalısınız. :wink:
 
####  7)  ViewData, ViewBag, TempData farkları nelerdir?

- ViewData;
  - ViewData ViewDatadictionary sınıfından türetilen bir dictionary nesnesidir. 
  - ViewData ControllerBase sınıfının bir özelliğidir.
  - ViewData Controller üzerinden View tarafına veri çekmek için kullanılır.
  - SAdece geçerli istek sırasında okunabilir.
  - Yönlendirme sonrasında kendini imha eder,null değer alır.
  - Veriyi değişkene almak için __**```tip dönüşümü yapmanız gerekir.```**__
  
- ViewBag
  - c# 4.0 ile gelen dinamik veri tipi özelliklerden faydalanır.
  - Temelde ViewData gibi Controller üzerinden View tarafına veri çekmek için kullanılır.
  - ViewBag ControllerBase sınıfının bir özelliğidir.
  - Sadece geçerli istek sırasında okunabilir.
  - Yönlendirme sonrasında kendini imha eder,null değer alır.
  - Veriyi değişkene almak için __**```tip dönüşümü yapmanız gerekmez.```**__
  
- TempData
  - TempDataDictionary sınıfından türetilen kısa ömürleri sessionda depolanan bir dictionary nesnesidir.
  - ViewBag ControllerBase sınıfının bir özelliğidir.
  - Tempdata geçerli istekten sonraki siteğe veri aktarmak için kullanılabilir.(Yönlendirme yaptığınızda veri default olarak bir defaya mahsus hafızada kalacaktır.)
  - Yaşam süresi çok kısadır.edef view tamamen yüklendiğinde kendini imha eder.
  - Veriyi değişkene atmak için   __**```tip dönüşümü yapmanız gerekir.```**__
