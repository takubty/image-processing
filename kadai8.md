#課題8レポート

ORG = imread('gunma-IMG_7896_TP_V.png');  
ORG = rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar;  
原画像を白黒濃淡画像に変換して表示
![fig8_1](/image/fig6_1.png)  
図1 白黒濃淡画像  

IMG = ORG > 128;  
imagesc(IMG); colormap(gray); colorbar;  
しきい値を128にし，画像を2値化して表示  
![fig8_2](/image/fig6_2.png)  
図2 2値画像  

IMG = bwlabeln(IMG);  
imagesc(IMG); colormap(jet); colorbar;  
bwlabelnで2値化した画像の連結部分にラベルをつけて表示  
![fig8_3](/image/fig8_3.png)  
図3 ラベル付けした画像  

考察  
2値化された画像で白，黒が連続した画素に同じ番号を割り振る処理をラベリングという．これを用いて同じ番号ごとの画素数や幅，高さなどの特徴量を求めることで，欠陥検査や分類処理などが行われる．  
