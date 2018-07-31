# cosine_similarity.py

>How to find the percentage of similarity between two documents? A python script that finds the percentage of similarity between two documents using the cosine similarity algorithm.

İki döküman arasındaki benzerlik yüzdesini bulmak için kullanılan kosinüs benzerliği yönteminin ayrıntılarını [şu linkteki dökümandan](http://bilgisayarkavramlari.sadievrenseker.com/2012/11/08/kosinus-benzerligi-cosine-similarity-2/) okuyabilirsiniz. Bu yöntemi kullanarak benzerlik yüzdesini bulan bir python scripti yazdım, ben bunu anlatacağım.

Not: Dökümanlarda geçen kelimelerin hangi dökümanda kaç defa geçtiğinin hesaplamasına girmeyeceğim. Bu aşamanın yapıldığını varsayarak, sonrasını anlatacağım.
Kısaca işlem adımları:

* Her iki dükümanda geçen kelimelerden, kaç defa geçtiği (frekansı) de hesaplanarak vektör oluşturacağız.
* İki vektör arasındaki açının derecesi üzerinden dökümanların benzerlik yüzdesini bulacağız.(cosine similarity)

## Gereksinimler:

scipy modülüne ihtiyacmız olacak. Önce onu kuralım.

` $ pip3 install scipy`
