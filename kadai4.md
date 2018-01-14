# 課題4レポート

原画像を白黒濃淡画像へ変換した画像を表示する．  
ORG=imread('gunma-IMG_7896_TP_V.png');  
ORG=rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar;  
![fig4_1](/image/fig4_1.png)
図1 白黒濃淡画像

画素の濃度ヒストグラムを表示する．  
imhist(ORG);  
![fig4_2](/image/fig4_2.png)  
図2 ヒストグラム  

考察  
ヒストグラム表示することによりどのあたりの濃度値にピークがあるのか一目でわかる．  
この画像の場合30,100,130,160,220あたりにピークがある．  
