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

OCR hataları giderme ( prompt değişikliği yapılacak, chunk değeri değişiklik)
LLM akışlı yanıt denenebilir( yavaş gelen cevapları hızlı göstermek için)


