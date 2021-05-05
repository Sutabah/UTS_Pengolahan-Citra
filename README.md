# Tampilan GUI dari Guidenya  

![1](https://user-images.githubusercontent.com/81844622/117101243-f2cf2880-ad9f-11eb-990a-a2042ac3743d.jpg)

![2](https://user-images.githubusercontent.com/81844622/117101366-4b062a80-ada0-11eb-9063-d27514a3ca54.jpg)

# Tampilan GUI dari hasilnya

![3](https://user-images.githubusercontent.com/81844622/117101430-6d984380-ada0-11eb-8a8a-6662f48e5e67.jpg)

Berikut Source codenya :

% Untuk menampilkan backgroudnya
hback = axes('unit','normalized','position',[0 0 1 1]);
uistack(hback,'bottom');
[back map] = imread('background.jpg');
image(back)
colormap(map)
set(hback,'handlevisibility','off','visible','off');

[filename,pathname] = uigetfile({'*.jpg','*.png'});
Citra1 = imread([pathname, filename]);

%Menampilkan Gambar di axes
axes(handles.axes1);
imshow(Citra1);

%Mengubah gambar Rgb
R = Citra1(:,:,1);
G = Citra1(:,:,2);
B = Citra1(:,:,3);
Red = cat(3,R,G*0,B*0);
Green = cat(3,R*0,G,B*0);
Blue = cat(3,R*0,G*0,B);

%Menampilkan Histogram
%Menampilkan Gambar di Axes2
citra2 = Red
axes(handles.axes2);
imshow(citra2);

%Menampilkan Gambar di Axes3
citra3 = Green 
axes(handles.axes3);
imshow(citra3);

%Menampilkan Gambar di Axes4
citra4 = Blue
axes(handles.axes4);
imshow(citra4);

%Menampilkan histogram red di Axes 5
axes(handles.axes5);
histogram(R(:),256,'FaceColor','r','EdgeColor','r')
set(gca,'XLim',[0 255])
set(gca,'YLim',[0 15000])
grid on

%Menampilkan histogram red di Axes 6
axes(handles.axes6);
histogram(G(:),256,'FaceColor','g','EdgeColor','g')
set(gca,'XLim',[0 255])
set(gca,'YLim',[0 15000])
grid on

%Menampilkan histogram red di Axes 7
axes(handles.axes7);
histogram(B(:),256,'FaceColor','b','EdgeColor','b')
set(gca,'XLim',[0 255])
set(gca,'YLim',[0 15000])
grid on

%Menampilkan histogram Rgb di axes 8
axes(handles.axes8);
histogram(B(:),256,'FaceColor','b','EdgeColor','b')
set(gca,'XLim',[0 255])
set(gca,'YLim',[0 15000])
hold on
histogram(G(:),256,'FaceColor','g','EdgeColor','g')
set(gca,'XLim',[0 255])
set(gca,'YLim',[0 15000])
histogram(R(:),256,'FaceColor','r','EdgeColor','r')
set(gca,'XLim',[0 255])
set(gca,'YLim',[0 15000])
hold off


