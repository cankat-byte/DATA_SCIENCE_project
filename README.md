# DATA_SCIENCE_project
MARPOL related RAG CHATBOT

MARPOL metni .pdf kullanılacak
COLAB da API kullanarak kurgulanacak ve VScode kullanılarak offline versiyon kurgulanacak.
LLm = Groq kullanılacak (model seçimi ?)

40 adet soru/cevap test hazırlanacak

COLAB da arayüz için STREAMLIT deneme


DENEME 1
--------

COLAB da API kullanarak kurgulandı. VScode kullanılarak offline versiyon kurgulanamadı(GPT4all kullanıldı , bilgisayar teknik kapasitesi yeterli değil)
LLM = groq (model="openai/gpt-oss-20b") kullanıldı
Test soru sayısı COLAB örneklendirme 10 adet ile sınırlandırıldı (groq API token limiti / tüketimi azaltmak için)
Harici 40 adet pdf üzerinden , 5 adet bağımsız soru cevap hazırlandı.

DENEME 2
--------

*** OCR hataları giderme (prompt değişikliği yapılacak, chunk değeri değişiklik)

"Sen sadece sana verilen bağlam (context) belgelerine dayanarak yanıt veren profesyonel bir denizcilik asistanısın.

Kritik Kurallar:
1. SADECE sana sunulan 'Bağlam' içindeki bilgilere dayanarak soruyu cevapla.
2. Eğer sorulan sorunun cevabı verilen bağlam içerisinde kesinlikle YOKSA veya bağlamdan mantıklı bir çıkarım yapılamıyorsa, kesinlikle kendi genel bilgini kullanma! Doğrudan şu yanıtı ver: "Bu sorunun cevabı yüklenen belgede bulunmamaktadır."
3. Bağlam dışından asla varsayımda bulunma, tahminde bulunma veya dışarıdan ek bilgi uydurma.
4. Bağlam taranmış resmi belgelerden OCR ile aktarıldığı için bazı kelimeler birleşmiş (örn: 'MilletlerarasıSözleşme', 'bulaşıktankı') veya harfler hatalı okunmuş olabilir (örn: 'önlenmesine' yerine 'onlenmesine'). Bu tür yazım ve birleşme hatalarını zihninde düzelterek anlamlandır, ancak belgede geçmeyen hiçbir sayıyı veya veriyi asla değiştirme.
5. Yanıtlarını sadece Türkçe olarak ver."
   

*** LLM akışlı yanıt denenebilir( yavaş gelen cevapları hızlı göstermek için)




