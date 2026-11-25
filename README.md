# Seismograph Scanner

4 kripto borsasının spot piyasasını tek bir evrende birleştiren ve kendi skorunun gerçekten bir şey öngörüp öngörmediğini de ölçen altcoin tarayıcısı. Tek bir HTML dosyasından oluşur, tarayıcıda çalışır, kurulum gerektirmez.

> *English summary: a single-file browser scanner that merges Binance, Bybit, OKX and KuCoin USDT spot markets, scores coins on a price-layer composite, and validates that composite with a rolling information-coefficient (IC) backtest plus a forward test on saved daily snapshots.*

## Özellikler

- **Dört borsa, tek evren:** Binance, Bybit, OKX ve KuCoin USDT spot pariteleri sembole göre birleştirilir, hacimler toplanır. Bir borsa erişimi engellerse tarama diğerleriyle devam eder.
- **Stablecoin ve tokenize hisse filtresi:** Bu varlıklar isimlerine göre değil, fiyat davranışlarına göre ayıklanır. Günlük hareketi %0,4'ün altında kalan ve fiyatı 1$ civarında olan varlık stablecoin sayılır. Hafta sonu hareketi hafta içinin %35'inin altında kalan varlık, hafta sonu kapalı bir piyasayı takip ediyor kabul edilir.
- **Skorlanan fiyat katmanı ve skorlanmayan temel katman:** Geliştirici aktivitesi (GitHub), haber hızı, katalizörler, staking ve token kilit açılımları gösterilir ama skora katılmaz. Bunun nedeni, bu verilerin her coin için bulunmaması ve test edilebilecek ücretsiz geçmiş verilerinin olmaması.
- **Geriye dönük doğrulama:** Kompozit skor, geçmişteki 18 tarihte (14 gün arayla, yaklaşık 8 ay) yalnızca o tarihe kadarki veriyle yeniden hesaplanır. Sonraki 14 günün getirisiyle sıra korelasyonu (IC) ölçülür ve null dağılımıyla karşılaştırılır.
- **İleriye dönük test:** Her günün ilk taraması tarayıcıya kaydedilir. Belirli bir süre sonra gerçek fiyat hareketiyle karşılaştırılır. Bu, skor üretildiği anda bilinmeyen verilerle yapılan temiz bir örneklem dışı testtir.

## Kullanım

`index.html` dosyasını tarayıcıda açman yeterli. Ayarlar bölümünden isteğe bağlı ücretsiz anahtarlar eklenebilir (GitHub token, CoinGecko demo, Mobula). Bu anahtarlar yalnızca senin tarayıcında kalır ve sadece ait oldukları servise gönderilir. Tarayıcının CORS engeline takılan borsalar için ücretsiz bir Cloudflare Worker proxy seçeneği de var.

## Nasıl geliştirildi

Tarama mantığı, filtreler ve doğrulama tasarımı bana ait. Kod [Claude Code](https://claude.com/claude-code) ile yazıldı.

Yatırım tavsiyesi değildir.
