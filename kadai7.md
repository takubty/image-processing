#課題7レポート

ORG = imread('gunma-IMG_7896_TP_V.png');  
ORG = rgb2gray(ORG);  
imhist(ORG);  
原画像を読み込み，濃淡のヒストグラムを作成し表示する．  
![fig7_1](/image/fig7_1.png)  
図1 ヒストグラム

ORG = double(ORG);  
mn = min(ORG(:));  
mx = max(ORG(:));  
ORG = (ORG-mn)/(mx-mn)*255;  
imagesc(ORG); colormap(gray); colorbar;  
最小濃度値を引いた値を最大値と最小値の差で割り，255をかけることでダイナミックレンジを0~255にすることができる．  
![fig7_2](/image/fig7_2.png)  
図2 ダイナミックレンジ変更後の画像  
![fig7_3](/image/fig7_3.png)  
図3 ヒストグラム  

考察  
ダイナミックレンジを変更する作業で，ORGの値が小数点以下を含む場合があるので，double(ORG)を用いて変数の型を変更している．それをもとの8ビット符号なし整数に戻すために使われているのがunit8であることがわかった．
