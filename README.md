# debe to kindle
<img src="img\dtk1.jpg" width="700">

Mini Tool to lovers of debe from eksisozluk (one of the most famous website -reffered as collaborative dictionary like 
reddit- in Turkey) for pushing debe (Most Liked Entries of Yesterday) to kindle every day via Github Actions.

# Nasıl Kullanırım ?
1. Öncelikle kullanacağınız mail adresininizin SMTP/IMAP ayarlarının var olduğunu düşünüyorum. Eğer yapılmamış veya emin
değilseniz **Oluşabilecek Hatalar** kısmına bakın. Sonra [buradan](https://myaccount.google.com/lesssecureapps) 
"Daha az güvenli uygulama erişimi"'ne izin verin.
2. Projeyi fork'layın. (Github üyeliğiniz yoksa tabi önce üye olun ve sağ üstte yer alan Fork'a tıklayın)
3. `Settings > Secrets`'a girip, sağ üstte yer alan `New Depository Secret` ile aşağıda yer alan üç adet Secret'i oluşturun.
    * `KINDLE_MAIL` : kindle mail adresiniz. (isim@kindle.com)
    * `MAIL_NAME` : gönderilecek mail adresiniz (durumsever@gmail.com)
    * `MAIL_PASSWORD` : mail adresinizin şifresi.
4. Dilerseniz gönderim saatini `.github/workflows/debe-to-kindle.yml` dosyasında yer alan `cron: "1 7 * * *"` kısmından
değiştirebilirsiniz. İkinci sayı saati ilk sayı ise dakikayı belirtiyor. 09:20 için `cron: "20 9 * * *"` gibi. 
(Saatler UTC üzerinden)
5. `debe-to-kindle-push.yml` ve `debe-to-kindle.yml` adında iki adet action var. Push değişiklik yapıldığında diğeri ise
günlük olarak mail gönderir. Kurulum yaptığınızda günlük mail gönderilir ancak ayarları yeniden yaptıktan sonra deneme yapmak için :
   * Repository anasayfasındaki `yeşil / kırmızı işaret > Details`'i tıklayın. Açılan sayfadan `Re-run all jobs`'a tıklayın.
   * Veya `Actions > debe-to-kindle-push`'a tıklayıp orada yer alan son Action sayfasından `Re-run all jobs`'a tıklayın.
6. Eğer bu adımda mail gönderiminde hata var ise [Bu](https://accounts.google.com/b/0/DisplayUnlockCaptcha) 
sayfa üzerinden (sanıyorum ki bir kez olarak) **Devam Et** seçeneğine tıklayın.
7. Debe'yi kindle üzerinden okumanın keyfini çıkarın :)

# Mail Ayarları & Oluşabilecek Hatalar
Melun Gmail, kendini korumayı görev edindiği için giriş yapamama hatalarını pek çok çeşitli yollar ile alabilirsiniz. Bu
sebepten [bu](https://support.google.com/mail/answer/7126229) sayfa üzerindeki 1. Adım kısmında yazanları ve 
**Sorun Giderme** kısmındaki adımları büyük bir dikkat ile tamamlayın. Ayrıca [bu](https://myaccount.google.com/lesssecureapps)
sayfa üzerinden "Daha az güvenli uygulama erişimi"'ne izin vermelisiniz.
* İki adımlı uygulama kullanıyorsanız, kendi şifreniz yerine uygulama şifresi ile giriş yapmanız gerekiyor olabilir. Yukarıda
yer alan linkin **Sorun Giderme** kısmında ne yapacağınızı bulabilirsiniz.
* Son ve pek önemli olarak [şu](https://accounts.google.com/b/0/DisplayUnlockCaptcha) sayfada yer alan Devam Et düğmesine
tıklamayı ihmal etmeyin. Yine yukarıdaki linkte yer alan **Sorun Giderme** kısmında aynı link yer alıyor. Yaptığım çeşitli
denemeler sırasında bu linki en az bir kere tıklamadan mailin gönderildiğine şahit olmadım.

# Geri Bildirim
Bir hata bulduysanız (o sizin kullanıcı hatanızdır, gayet çalışıyor işte), veya (daha ne eklenebilir emin değilim ama) 
yeni bir özellik eklenmesini dilerseniz mail atmaktan, pull requests göndermekten, sözlük üzerinden mesaj atmaktan ve dua
etmekten geri durmayın.