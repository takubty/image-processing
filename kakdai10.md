#課題10レポート

ORG = imread('gunma-IMG_7896_TP_V.png');  
ORG = rgb2gray(ORG);  
imagesc(ORG); colormap('gray'); colorbar;  
白黒濃淡画像に変換し表示  
![fig10_1](/image/fig6_1.png)  
図1 白黒濃淡画像  

IMG = edge(ORG,'prewitt');  
imagesc(IMG); colormap('gray'); colorbar;  
白黒濃淡画像からプレウィット法を使用してエッジを検出して表示する．  
![fig10_2](/image/fig10_2.png)  
図2 エッジ抽出画像  

IMG = edge(ORG,'sobel');  
imagesc(IMG); colormap('gray'); colorbar;  
ソベル法でさらにエッジ抽出をして表示  
![fig10_3](/image/fig10_3.png)  
図3 エッジ抽出画像  

IMG = edge(ORG,'canny');  
imagesc(IMG); colormap('gray'); colorbar;  
キャニー法でエッジを抽出して表示  
![fig10_4](/image/fig10_4.png)  
図4 エッジ抽出画像  

考察  
3画素ずつを対にして濃度の変化点を抽出する方法をプレウィット法という，また，この方法の中心がその影響を強調した処理をソベル法という．エッジ検出処理を重ねていくと濃度の濃い画像になっていくのだと思ったが，輪郭を検出する処理なのでそうはならなかった．
