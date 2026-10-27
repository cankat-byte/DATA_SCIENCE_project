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
   

*** LLM akışlı yanıt denenebilir( yavaş gelen cevapları hızlı göstermek için) / Deneme 3 sonunda hız yeterli , gerek yok.


DENEME 3
--------

hem PDF parçalama hem de streamlit arayüz oluşumu aşamalarında ;

embeddings model = distiluse-base-multilingual-cased-v1 kullanılacak ( Üstün Türkçe Anlama Yeteneği , Çok Dilli Esneklik- Bilgi Kaybını Önler ,  Bilgi Yoğunluğu ve Hafiflik (Distilled Model)

chunk_size= 1000 , chunk_overlap=250 yapıldı
app.py llm temperature = 0.0  yapıldı

40 + 5 adet soru testi yapıldı

* Chatbot kapsam genişletme ? düşünülecek ( denizcilik sözleşme metinleri ?)
  ** COLAB ile arayüz oluşturma (streamlit alternatif) yapılabilir
    *** Masaüstüne uygulama ( :) yapılabilir

10 adet test sorusu her çalışstırldığında değişkenlik gösteriyor !!!

DENEME 4
--------

PDF parçalama aşaması 5 dk sürüyor. / süreyi azaltmak için daha hızlı ve hafif bir gömme modeli kullanmak!!
10 adet test soru/cevap son çalıştırmada 1 yanlışa düştü.
Sadece MARPOL değil başka sözleşme metinlerini de yükleyerek genel denizcilik üzerine bir kurgu planı
Masaüstüne uygulama arayüzü yapılacak.

DENEME 5
--------
* LLM = groq (model="openai/gpt-oss-20b") kullanıldı
* Embedding - model = "sentence-transformers/distiluse-base-multilingual-cased-v1" / hugging face kullanıldı
* chunk_size : 800 / chunk_overlap: 200 kullanıldı
* vektör boyutu: 512 / arama ayarı (k) : 6 kullanıldı
* rate_limit için = invoke_with_retry fonksiyonu VE yapay gecikme (time.sleep): 3,5sn kullanıldı
  
* kütüphaneler ;
Doküman İşleme ve Veri Hazırlama - pymupdf (PyMuPDFLoader) , langchain-text-splitters (RecursiveCharacterTextSplitter)
Yapay Zeka, Vektörleştirme ve Gömme (Embedding) - langchain-huggingface (HuggingFaceEmbeddings), sentence-transformers ,
langchain-core (InMemoryVectorStore)
Büyük Dil Modeli (LLM) Entegrasyonu - langchain-groq (ChatGroq), groq (RateLimitError)
Kullanıcı Arayüzü ve Sunum (UI) -  gradio , streamlit , ipywidgets

3 arayüz de başarıyla çalıştırıldı.

       




