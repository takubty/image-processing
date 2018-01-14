# 課題5レポート

ORG=imread('gunma-IMG_7896_TP_V.png');  
ORG = rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar;  
原画像を白黒濃淡が層へ変換し表示
![fig5_1](/image/fig5_1)
図1 白黒濃淡画像

H = imhist(ORG);  
myu_T = mean(H);  
max_val = 0;  
max_thres = 1;  
for i=1:255  
C1 = H(1:i);  
C2 = H(i+1:256);  
n1 = sum(C1);  
n2 = sum(C2);  
myu1 = mean(C1);  
myu2 = mean(C2);  
sigma1 = var(C1);  
sigma2 = var(C2);  
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2);  
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2);  
if max_val<sigma_B/sigma_w  
max_val = sigma_B/sigma_w;  
max_thres =i;  
end  
end  
 
IMG = ORG > max_thres;  
imagesc(IMG); colormap(gray); colorbar;  

ヒストグラムを2つに分け，それぞれのクラス間の分散の各クラス内分散に対する日の値が最大になるようにしきい値を決め，画像を表示する．  
![fig5_2](/image/fig5_2.png)  
図2 2値化した画像  

考察  
対象物と背景の濃度がそれぞれ最もよくまとまり，かつ対象物と背景の違いが際立つようにしきい値を求める方法を判別分析法という．
この画像の場合，青空の濃淡に差があるため，うまく差をつけることができなくなってしまったのだと考えられる．
人物や動物を撮った画像のほうがより差が出ると思う．
