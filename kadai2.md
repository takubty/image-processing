# 課題2レポート

課題1と同様に原画像をダウンロードし，使用する．  
ORG=imread('gunma-IMG_7896_TP_V.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;  
imagesc(ORG); axis image; % 画像の表示  
rgb2grayによりカラーイメージをグレースケール強度イメージへ変換する．  
また，colormap(gray)によりクレー1色のカラーマップを作成し，画像を表示する．  
![fig2_1](/image/fig2_1.png)  
図1 モノクロ化した原画像  

8ビットの階調は0~255の256階調なので中間の128以上とすると2階調となるため，  
IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  
とすると2階調画像が表示される．  
![fig2_2](/image/fig2_2.png)  
図2　2階調画像  

同様に，64以上，128以上，196以上のものを足すと，4階調となる．  
IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  
![fig2_3](/image/fig2_3.png)  
図3 4階調画像  

同様にして，8階調画像を作成した．  
IMG0 = ORG>32;  
IMG1 = ORG>64;  
IMG2 = ORG>96;  
IMG3 = ORG>128;  
IMG4 = ORG>160;  
IMG5 = ORG>192;  
IMG6 = ORG>224;  
IMG7 = ORG>256;  
IMG_1 = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6 + IMG7;  
imagesc(IMG_1); colormap(gray); colorbar;  axis image;  
![fig2_4](/image/fig2_4.png)  
図4 8階調画像  
