# Tampilan GUI dari Guidenya  

![1](https://user-images.githubusercontent.com/81844622/117101243-f2cf2880-ad9f-11eb-990a-a2042ac3743d.jpg)

![2](https://user-images.githubusercontent.com/81844622/117101366-4b062a80-ada0-11eb-9063-d27514a3ca54.jpg)

# Tampilan GUI dari hasilnya

![3](https://user-images.githubusercontent.com/81844622/117101430-6d984380-ada0-11eb-8a8a-6662f48e5e67.jpg)

# Berikut Source codenya :

% Untuk menampilkan backgroudnya</br>
hback = axes('unit','normalized','position',[0 0 1 1]);</br>
uistack(hback,'bottom');</br>
[back map] = imread('background.jpg');</br>
image(back)</br>
colormap(map)</br>
set(hback,'handlevisibility','off','visible','off');</br>

% Untuk callback pushbutton</br>
[filename,pathname] = uigetfile({'*.jpg','*.png'});</br>
Citra1 = imread([pathname, filename]);</br>

 %Menampilkan Gambar di axes</br>
axes(handles.axes1);</br>
imshow(Citra1);</br>

 %Mengubah gambar Rgb</br>
R = Citra1(:,:,1);</br>
G = Citra1(:,:,2);</br>
B = Citra1(:,:,3);</br>
Red = cat(3,R,G*0,B*0);</br>
Green = cat(3,R*0,G,B*0);</br>
Blue = cat(3,R*0,G*0,B);</br>

 %Menampilkan Gambar di Axes2</br>
citra2 = Red</br>
axes(handles.axes2);</br>
imshow(citra2);</br>

 %Menampilkan Gambar di Axes3</br>
citra3 = Green </br>
axes(handles.axes3);</br>
imshow(citra3);</br>

 %Menampilkan Gambar di Axes4</br>
citra4 = Blue</br>
axes(handles.axes4);</br>
imshow(citra4);</br>

 %Menampilkan histogram red di Axes 5</br>
axes(handles.axes5);</br>
histogram(R(:),256,'FaceColor','r','EdgeColor','r')</br>
set(gca,'XLim',[0 255])</br>
set(gca,'YLim',[0 15000])</br>
grid on</br>

 %Menampilkan histogram red di Axes 6</br>
axes(handles.axes6);</br>
histogram(G(:),256,'FaceColor','g','EdgeColor','g')</br>
set(gca,'XLim',[0 255])</br>
set(gca,'YLim',[0 15000])</br>
grid on</br>

 %Menampilkan histogram red di Axes 7</br>
axes(handles.axes7);</br>
histogram(B(:),256,'FaceColor','b','EdgeColor','b')</br>
set(gca,'XLim',[0 255])</br>
set(gca,'YLim',[0 15000])</br>
grid on</br>

 %Menampilkan histogram Rgb di axes 8</br>
axes(handles.axes8);</br>
histogram(B(:),256,'FaceColor','b','EdgeColor','b')</br>
set(gca,'XLim',[0 255])</br>
set(gca,'YLim',[0 15000])</br>
hold on</br>
histogram(G(:),256,'FaceColor','g','EdgeColor','g')</br>
set(gca,'XLim',[0 255])</br>
set(gca,'YLim',[0 15000])</br>
histogram(R(:),256,'FaceColor','r','EdgeColor','r')</br>
set(gca,'XLim',[0 255])</br>
set(gca,'YLim',[0 15000])</br>
hold off</br>

# Link Youtube : https://www.youtube.com/watch?v=IlH7HoAcHOI

