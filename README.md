# İşaret Dili Tanıma Modeli

Bu proje, makine öğrenimi teknikleri kullanarak işaret dili jestlerini metne dönüştürmeyi amaçlamaktadır. TensorFlow, OpenCV, MediaPipe ve scikit-learn gibi kütüphanelerle geliştirilmiş olan model, yüz, el ve vücut anahtar noktalarını kullanarak jestleri sınıflandırmaktadır.

## Proje Genel Bakış

Bu proje, MediaPipe kullanarak anahtar noktaların tespit edilmesi ve TensorFlow ile bu noktaları sınıflandırmak için bir modelin eğitilmesini içerir. Model, "merhaba", "teşekkürederim", "evet" gibi belirli işaret dili jestlerini tanımak üzere tasarlanmıştır. Anahtar noktalar, MediaPipe'in Holistic modeli kullanılarak el, yüz ve vücut landmark'larından çıkarılmaktadır.

## Kullanılan Teknolojiler
- Python
- TensorFlow
- Matplotlib
- OpenCV
- MediaPipe
- scikit-learn


## Model Mimarisi
Model, istiflenmiş bir LSTM (Long Short-Term Memory) ağı kullanılarak oluşturulmuştur. Model katmanlarının özeti aşağıdaki gibidir:

- Üç LSTM Katmanı: Sırasıyla 64, 128 ve 64 birimle.
- İki Yoğun (Dense) Katman: Veri işleme ve sınıflandırma için.
- Softmax Çıkış Katmanı: Jest sınıflandırması için.

Model, kategorik çapraz entropi kayıp fonksiyonu kullanılarak yüksek doğrulukla jestleri tanımayı hedeflemektedir.

## Veri Toplama
Veri toplama, el, yüz ve vücut landmark'larından anahtar noktaların yakalanmasını içerir. Proje, üç ana jesti desteklemektedir: "merhaba", "teşekkürederim" ve "evet". Veriler, bir web kamerası kullanılarak canlı video yakalama ile 30 karelik videolar halinde kaydedilir.

## Modelin Eğitilmesi
Veriler toplandıktan sonra, LSTM modeli eğitilir.

## Değerlendirme
Eğitilen model, karmaşıklık matrisi ve doğruluk skoru kullanılarak değerlendirilir.



# Sign Language Recognition Model
This project aims to convert sign language gestures into text using machine learning techniques. The model, developed with libraries such as TensorFlow, OpenCV, MediaPipe, and scikit-learn, classifies gestures by utilizing keypoints of the face, hands, and body.

## Project Overview
This project includes the detection of keypoints using MediaPipe and the training of a model to classify these points with TensorFlow. The model is designed to recognize specific sign language gestures such as "hello" "thank you" and "yes" Keypoints are extracted using MediaPipe's Holistic model, which includes landmarks for the hands, face, and body.

## Technologies Used
- Python
- TensorFlow
- Matplotlib
- OpenCV
- MediaPipe
- scikit-learn
## Model Architecture
The model is constructed using a stacked LSTM (Long Short-Term Memory) network. A summary of the model layers is as follows:

- Three LSTM Layers: With 64, 128, and 64 units respectively.
- Two Dense Layers: For data processing and classification.
- Softmax Output Layer: For gesture classification.

The model aims to recognize gestures with high accuracy using the categorical cross-entropy loss function.

## Data Collection
Data collection involves capturing keypoints from hand, face, and body landmarks. The project supports three main gestures: "hello" "thank you" and "yes." Data is recorded in 30-frame videos using a webcam for live video capture.

## Model Training
After data collection, the LSTM model is trained.

## Evaluation
The trained model is evaluated using a confusion matrix and accuracy score.

