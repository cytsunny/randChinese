# 中文亂文隨機生成器

## 為什麼需要這個亂文生成器？

現在比較好的亂文生成器主要都是直接在網上生成，只可以人手複製到要用的地方。如果只是用來設計時試排版是沒問題的，但是有如果需要大量生成就不太方便。（例如做 unit test 的時候想要中文輸入）

另一個常見的做法就是在 UTF8 中指定漢字一段，再隨機在抽出文字。這樣生出來的字大概是這樣的：

> 悍箳寊貈绺鶭缂迩泜輅歍銋囄轴埄侭鐸攛塰俟兯锁沟忍鳚苚鉤

雖然生出來的是方塊字，但太陌生的字看起來還是不像是中文。（事實上也真的可能不是中文，因為那段叫 CJK － Chinese, Japanese, Korean，即中文正體字、簡體字、日本漢字和韓國用的漢字都包含在內。因為有些的確是一樣的，所以這不能怪 UTF8。）

這個生成器使用香港課程發展處中國語文教育組的《[中英文對照香港學校中文學習基礎字詞](http://www.edbchinese.hk/lexlist_en/)》中記載的正體字，只收錄大概 4000 多個在香港中小學會接觸到的正體字。生出來的字大概是這樣的：

> 攻格瑣雇嬪腐楓蹉臭舖黏沖賒廬侮彭疼呃淅龐

好吧，看起來還是有點太複雜了。所以我把字再根據 4000  多個字中抽取 500 個。生出來的字大概是這樣：

> 朽乏斤允叉企十妃划巧毛任只舌吁冬低乙友弘

## 如何使用這個生成器？
下載 randChinese.php，然後：

```php
include ('path/to/your/download/randChinese.php') //只有你知道你把代碼下載到哪裡。請自行填寫正確的路徑。
use RandChinese\RandChinese;
echo RandChinese::phase(); //沒有數字的話預設生成 20 個中文字
echo '\n';
echo RandChinese::phase(40);//你也可以輸入想要的長度
echo '\n';
echo RandChinese::phase(20, 2000); //後面的數字決定複雜程度，可以是任何小於 4000 的數字
```

## 未來可能會增加的功能
實際做出來的時間視乎有多少人想要，以及多少人使用這個生成器。

1. 支援 composer

2. 增加「加入標點符號」這個選項

3. 選擇生成較顯淺的中文字（主要看筆劃決定難度）

4. 生成中文名稱

5. 製作 Javascript 版本
