# Deep Learning
 Pretrained model and DEC model for clustering cafe interior images to classify cafe according to atmosphere. (after training model, we did survey about our result)

<h2>Collecting Image</h2>
Crowling_cafe_images.ipynb


The format of file is ipynb. 
It's the code of crowling cafe image from naver maps.
Naver Map provide us maximum 70 lists of cafe per one search term.
This code corwl 10 image per one cafe.
Processing Exception is not perfect. So If you experience Exception problem, you have to try to crowl next image.

<h2>Pretrained model</h2>
I upload 3 models. They trained about 10143 cafe images.


I don't think they are perfect. But last model(Places365 - PCA extraction - kmeans clustering) is best model. 


All of them didn't train more. They just return feature extraction about cafe images. 


This site provide the code about Places365


https://github.com/AMANVerma28/Indoor-Outdoor-scene-classification



ResNet50 - kmeans clustering
-> Using ResNet50.ipynb

Places365 - kmeans clustering
> Using Places365.ipynb

Places365 - PCA extraction - kmeans clustering
> Using Places365.ipynb
 Pretrained model and DEC model for clustering cafe images
