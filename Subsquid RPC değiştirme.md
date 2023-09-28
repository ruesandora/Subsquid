SYNC SIKINTISI YAŞAYANLAR İÇİN RPC DEĞİŞİMİ
> 1- [Buradan](https://alchemy.com/?r=TU2Njk1MjUzNjQyM) üyelik oluşturuyoruz ve sağ üstte create new app diyip ETH (Hangi ağda seçtiyseniz siz ona göre RPC alın) mainnette kendi RPCmizi oluşturuyoruz. Api key kısmından  httpsli RPC linkimizi hazırda tutuyoruz.

> 2- Daha sonra Winscp ile `(deploy adımız)/src/processor.ts` isimli klasörü bulup içerisinde yer alan chain kısmını oluşturduğumuz RPC ile değiştiriyoruz.

> 3- Son olarak terminalde `sqd deploy --org isminiz ./isminiz` (isminiz yazan yerleri kendi deploy isminiz ile değiştirin) kodu ile deploy edin. Ve onaylara Yes diyin. Bu kadar
