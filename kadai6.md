#課題6レポート

ORG = imread('gunma-IMG_7896_TP_V.png');  
ORG = rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar;  
原画像をrgb2grayを用いて白黒濃淡画像へ変換した画像を表示  
![fig6_1](/image/fig6_1.png)  
図1 白黒濃淡画像  

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  
濃度値のしきい値を128より大きくすることで2値化した画像を表示する．  
![fig6_2](/image/fig6_2.png)  
図2 2値化した画像  

IMG = dither(ORG);  
imagesc(IMG); colormap(gray); colorbar;  
ディザ法を用いて2値化した画像を表示．  
![fig6_3](/image/fig6_3.png)  
図3 ディザ法により2値化した画像  

考察  
原画像の各画素の濃度値を画素位置によりあらかじめ決められたディザマトリクスの値と比較し，その大小関係で出力がその濃度値を決める方法をディザ法という．matlabではdither関数を用いることで実現できる．  
