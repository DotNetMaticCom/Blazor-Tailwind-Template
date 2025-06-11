# .NET 9 Blazor + Tailwind CSS Başlangıç Şablonu

Bu depo, **.NET 9 Blazor Web App** şablonu kullanılarak oluşturulmuş, modern ve temiz bir başlangıç projesi içerir. Proje, **Otomatik (Auto) Render Modu** ile yapılandırılmıştır; bu sayede hem sunucu tarafı render (SSR) hızını hem de istemci tarafı (WebAssembly) etkileşimini bir arada sunar.

Temel amacı, Tailwind CSS, PostCSS ve Autoprefixer entegrasyonu yapılmış, production (yayın) ve development (geliştirme) için gerekli build script'leri hazır, temiz bir altyapı sağlamaktır.

## Temel Teknolojiler ve Özellikler

* **.NET 9**: En güncel .NET altyapısı.
* **Blazor Web App**: Hem sunucu hem de istemci tarafı render yeteneklerini barındıran hibrit proje yapısı.
* **Tailwind CSS (v3.4.17)**: Hızlı ve modern arayüzler geliştirmek için utility-first CSS çatısı.
* **PostCSS & Autoprefixer**: CSS'in işlenmesi ve eski tarayıcılar için vendor prefix'lerin otomatik eklenmesi.
* **Temiz Proje Mimarisi**: Çözüm (`.sln`) ve proje (`.csproj`) dosyaları, kafa karıştırmayacak şekilde mantıksal olarak ayrılmıştır.
* **Hazır NPM Scriptleri**: Geliştirme ve yayın süreçleri için önceden yapılandırılmış `build:css` ve `watch:css` komutları.

## Kurulum ve Başlangıç

Bu şablonu kullanarak yeni bir projeye başlamak için:

1.  GitHub üzerinden **"Use this template"** butonunu kullanarak yeni bir depo oluşturun veya bu depoyu klonlayın.
2.  Terminalde projenin ana sunucu klasörüne gidin:
    ```bash
    # Örnek: cd ProjeAdin/ProjeAdin.Web
    cd TUYEM16.Web 
    ```
3.  .NET bağımlılıklarını yükleyin:
    ```bash
    dotnet restore
    ```
4.  NPM paketlerini kurun:
    ```bash
    npm install
    ```
5.  İlk Tailwind CSS derlemesini yapın:
    ```bash
    npm run build:css
    ```
6.  Projeyi çalıştırın:
    ```bash
    dotnet run
    ```

## Geliştirme Akışı

Verimli bir geliştirme süreci için iki terminal kullanılması önerilir. İki terminalde de `.../TUYEM16.Web` klasöründe olmalısınız.

* **1. Terminal (Tailwind CSS İzleyici):**
    Bu terminalde, stillerde yaptığınız değişikliklerin anında derlenmesi için `watch` komutunu çalıştırın.
    ```bash
    npm run watch:css
    ```

* **2. Terminal (.NET Projesi):**
    Bu terminalde, Blazor projesini `hot-reload` (anında yeniden yükleme) özelliğiyle birlikte çalıştırın.
    ```bash
    dotnet watch run
    ```

Bu iki komut çalışırken, `.razor` dosyalarında yaptığınız tüm HTML ve C# değişiklikleri tarayıcıya anında yansıyacaktır.

## Proje Yapısı

* `TUYEM16.Project.sln`: Ana çözüm dosyası.
* `/TUYEM16.Web`: Ana sunucu projesi.
    * `package.json`: NPM bağımlılıklarını ve script'lerini içerir.
    * `tailwind.config.js`: Tailwind CSS yapılandırma dosyası.
    * `postcss.config.js`: PostCSS ve Autoprefixer yapılandırması.
    * `wwwroot/app.css`: Tailwind için **girdi** CSS dosyasıdır.
    * `wwwroot/app.min.css`: Tailwind tarafından derlenerek oluşturulan **çıktı** CSS dosyasıdır. Bu dosya `.gitignore` içinde yer alır ve depoya dahil edilmez.
* `/TUYEM16.Web.Client`: İstemci tarafında (WebAssembly) çalışacak olan proje.
