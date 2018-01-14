# 課題3レポート

ORG=imread('gunma-IMG_7896_TP_V.png');  
ORG= rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar;  
原画像を入力し，白黒濃淡画像へ変換．  
![fig3_1](/image/fig3_1.png)  
図1 白黒濃淡画像  

IMG = ORG > 64;  
imagesc(IMG); colormap(gray); colorbar;  
輝度値が64以上の画素を1，それ以外を0に変換した画像を表示．  
![fig3_2](/image/fig3_2.png)  
図2 2値画像  

IMG = ORG > 128;  
imagesc(IMG); colormap(gray); colorbar;  
輝度値が128以上とそれ以外の2値に変換した画像を表示．  
![fig3_3](/image/fig3_3.png)  
図3 2値画像  
