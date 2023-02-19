# Camera-Based-Community-Watch-for-Illegal-Dumping-Yolo-v5-OpenCV-Computer-Vision-
Detecting illegal dumping action in modern cities using Computer Vision methods and helping societies to have cleaner environment.

# Abstract -
Illegal dumping is the practice of throwing waste or not useful items in the undesignated areas of the society. This practice leads to environmental and health hazards. Improper disposal of waste items is a bigger issue for the local authorities and private companies as well as a lot of money is spent to resolve this issue. According to waste generation statistics in 2019, the United States of America produced the third highest waste per capita annually. Illegal dumping seems to be a harmless act in the short run, but it has harmful long-term consequences that include land, soil, air, and water pollution. After the pandemic the situation has become even worse, there are almost more than 300 cases reported in Santa Cruz county which means on a daily average one case has been reported. Furthermore, San Jose state is imposing a fine of $10000 for illegal dumping action. Hence, I tried to solve the problem of illegal dumping action detection by coming up with an innovative solution. Using YOLO v5 to detect human, vehicle, license plate and trash. After detecting I was also using deep SORT for tracking the objects and the human to detect the illegal dumping action. The action is detected by a decision module where if the distance between the bounding box of the human and the trash is less than a certain threshold and then increases then it would be detected as an illegal dumping action. Our model can detect the objects and the dumping action in day as well as nighttime. I have used night vision dataset to make our model more enhanced and accurate in detecting trash and dumping action. Efficient and quick detection of illegal dumping action could be useful for the local authorities, so I trained our model on real- time examples as well as the COCO dataset for more accurate object detection. The project focuses on building a web application where a person can either upload a video or report illegal dumping and then the concerned authorities would be notified with the details of the incident. The model can identify trash with 97% accuracy.

# System Architeture -

![image](https://user-images.githubusercontent.com/78490598/219909250-08521a34-e06d-49d6-bdcb-db8d075bc991.png)

# Data Preprocess Pipeline -
1. About 2000 manually labels images and videos using labelImg and Roboflow. Will upload the link to drive and roboflow later.
2. For license plate detection we used pretrain ALPR-weights from https://github.com/pracool/ANPR-with-YoloV5. Thank you pracool for amazing repo and drawing easy steps for installation of weights and graphs. Also, I had own dataset for vehicles. TIP: you can find data on roboflow universe but it might take time.
3. Albumentation

# Data Preparation Process -

![image](https://user-images.githubusercontent.com/78490598/219909305-e45bacbd-ca90-421e-990e-f1850fffc989.png)

# Model Overview 
1. Three models: human detection, car-license-plate detection and trash detection
2. All the model files with best weights are uploaded on the repo under model folder.
3. Trash model was trained on 4500 images with augmentation, while license-plate with 2000 images and about 1500 images of human with pretrain weights of human crowd git repo.

# Results -

1. Results of Trash Detection model below -

![image](https://user-images.githubusercontent.com/78490598/219909362-63e52bc8-346b-489d-87a8-143db51e5baa.png)

2. Results on unseen data from robloflow universe. the confidence was set at 70%

![image](https://user-images.githubusercontent.com/78490598/219909371-e74ba0cc-6fad-4133-a668-dd3d2319ec3e.png)

# Tracking Objects -

Deepsort algorithm will be used to track objects and human. Same ID will be assigned to both human and trash based on the distance. As human go far from the ojbect will be marked as illegal dumping.

# Conclusion -

Illegal Dumping has become a serious issue. States like California have started charging a fine of up to $10,000. I have worked to solve this problem using machine learning and deep learning technologies. I divided the problem into three different parts which are object detection (garbage objects mainly), action detection and Vehicle license plate recognition. To find the best possible models I have iterated for each model several times (more than 300 epochs). I trained and evaluated each YOLOV5 model using mAps and were able to achieve overall 87% accuracy. For assigning IDs to each distinct class, a DeepSORT algorithm was introduced to each model. After that, based on trash halting within frame, I developed a straightforward dumping detection system. When a piece of trash is dumped, the closest vehicle or person is responsible for the act, and the information is output in a text file. Our Flask- created GUI incorporates the complete framework. According to our findings, our study was successful in identifying unlawful dumping in any surveillance camera frame.

# Future Work -

In the future, real time streaming videos could be monitored to help users receive consistent reports and identify the perpetrators. One can install high-resolution infrared camera for higher data quality for night images.

# Impact -

The project will greatly help the community to reduce and handle illegal dumping easily with help of alert system without constantly monitoring. This will reduce cost and manpower involved. The project helps make a social contribution by improving the health of society by reducing dumping on streets or communities. The project could inspire others in the future to work on similar project and implement the future work mentioned.
