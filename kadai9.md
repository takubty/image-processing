#課題9レポート

ORG = imread('gunma-IMG_7896_TP_V.png');  
ORG = rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar;  
白黒濃淡画像を表示  
![fig9_1](/image/fig6_1.png)  
図1 白黒濃淡画像  

ORG = imnoise(ORG,'salt & pepper',0.02);  
imagesc(ORG); colormap(gray); colorbar;  
白黒濃淡画像にオンとオフのピクセルである[salt&pepper]を付加して表示  
![fig9_2](/image/fig9_2.png)  
図2 ノイズ付加画像  

IMG = filter2(fspecial('average',3),ORG);  
imagesc(IMG); colormap(gray); colorbar;  
平滑化フィルタを用いノイズ除去した画像を表示  
![fig9_3](/image/fig9_3.png)  
図3 平滑化フィルタで処理した画像  

IMG = medfilt2(ORG,[3 3]);  
imagesc(IMG); colormap(gray); colorbar;  
メディアンフィルタでノイズ除去した画像を表示  
![fig9_4](/imege/fig9_4.png)  
図4  メディアンフィルタで処理した画像  

f=[0,-1,0;-1,5,-1;0,-1,0];  
IMG = filter2(f,IMG,'same');  
imagesc(IMG); colormap(gray); colorbar;  
設計したフィルタを通した画像を表示
![fig9_5](/image/fig9_5.png)  
図5 設計したフィルタで処理した画像  

考察  
画素ごとの濃度値の細かな変動をなくし，滑らかな画像にするフィルタを平滑化フィルタという．平滑化することで見やすい画像にすることができるが，本来の高周波成分も失ってしまう．また，返還後の濃度値を着目画素の近傍画素の濃度値の平均とするのではなくそれらの画素濃度の中央値とするフィルタをメディアンフィルタという．どちらもノイズの除去はできるが一長一短であるといえる．
