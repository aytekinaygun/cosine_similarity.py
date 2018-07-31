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


## Sonuç:

`Similarity : 26.98771675773639 %`

İki döküman birbirlerine %26 oranında benziyormuş.

## Test 1

Dökümanları birbirlerine biraz daha benzeştirip test edelim.

doc1 = {'social':16, 'steemit':9, 'internet':10, 'cyriptocoin':8, 'blockchain':15, 'steemdolar':15, 'blue':3, 'red':2, 'yellow':1}

doc2 =  {'social':18, 'steemit':11, 'internet':9, 'cyriptocoin':5, 'blockchain':60, 'steemdolar':40, 'upvote':20}

`Similarity : 82.78837878218168 %`

Gayet güzel. Yüzdenin artması sistemin çalıştığını gösteriyor.

## Test 2

Her iki dökümandaki kelimeler aynı olsun ama her kelimenin frekansları arasında 20 kat olsun.

doc1 = {'social':15, 'steemit':9, 'internet':10, 'cyriptocoin':8, 'blockchain':15, 'steemdolar':15, 'blue':3, 'red':2, 'yellow':1}

doc2 =  {'social':300, 'steemit':180, 'internet':200, 'cyriptocoin':160, 'blockchain':300, 'steemdolar':300, 'blue':60, 'red':40, 'yellow':20}

`Similarity : 100.0 %`

Bunu beklemiyordum doğrusu! Mükemmel bir sonuç.

## Test 3

Son testimizde de hiçbir kelime benzerliği olmasın.

doc1 = {'social':15, 'steemit':9, 'internet':10, 'cyriptocoin':8, 'blockchain':15, 'steemdolar':15, 'blue':3, 'red':2, 'yellow':1}

doc2 =  {'xxxxsocial':300, 'xxxxsteemit':180, 'xxxxinternet':200, 'xxxxcyriptocoin':160, 'xxxxblockchain':300, 'xxxxsteemdolar':300, 'xxxxblue':60, 'xxxxred':40, 'xxxxyellow':20}

`Similarity : 0.0 %`

Son testden de görüldüğü üzere algoritma gayet güzel çalışıyor.

Kaynaklar :
http://bilgisayarkavramlari.sadievrenseker.com/2012/11/08/kosinus-benzerligi-cosine-similarity-2/
https://stackoverflow.com/a/18424933

