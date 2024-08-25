# Yolov5 Detection Demo
YOLOv5 has been designed to be super easy to get started and simple to learn. We prioritize real-world results.
![Logo](https://user-images.githubusercontent.com/26833433/155040763-93c22a27-347c-4e3c-847a-8094621d3f4e.png)

## Contacts
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bangdd/)

## A - Demo
| Before training | After training |
| :----- | :---- |
| <img width="360" alt="image" src="https://github.com/user-attachments/assets/898234ac-dc6a-4da1-a55f-b963ea7d7453"> | <img width="365" alt="image" src="https://github.com/user-attachments/assets/8232613a-e8df-4efe-a8f7-67e3b2a44c64"> |

## B - Preparing
### Documents
- [Github Repo](https://github.com/ultralytics/yolov5)
- [Train custom data](https://docs.ultralytics.com/yolov5/tutorials/train_custom_data/#before-you-start)

### Installing
- [x] [Python](https://docs.python-guide.org/starting/install3/osx/#install3-osx)
- [x] [Conda](https://conda.io/projects/conda/en/latest/user-guide/getting-started.html)
- [x] [Pytorch](https://pytorch.org/get-started/locally/)

### Packaging
```bash
cd yolov5
pip install ultralytics
pip install -r requirements.txt  
```

### Inference with detect.py
```bash
python detect.py --weights yolov5s.pt --source 0                               # webcam
                                               img.jpg                         # image
                                               vid.mp4                         # video
                                               screen                          # screenshot
                                               path/                           # directory
                                               list.txt                        # list of images
                                               list.streams                    # list of streams
                                               'path/*.jpg'                    # glob
                                               'https://youtu.be/LNwODJXcvt4'  # YouTube
                                               'rtsp://example.com/media.mp4'  # RTSP, RTMP, HTTP stream
```

## --options
| No | --option                    | Meaning                                                                                                                                                                                                                      |
| :- | :-------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1  | `--img` <br>or <br>`--img-size`     | **Ý nghĩa**: Xác định kích thước ảnh đầu vào cho mô hình (ví dụ: --img 640 có nghĩa là ảnh đầu vào có kích thước 640x640).<br>**Mặc định**: 640.                                                                             |
| 2  | `--epochs`                  | **Ý nghĩa**: Số lượng chu kỳ (epochs) mà mô hình sẽ huấn luyện trên tập dữ liệu. Một epoch là một lần duyệt qua toàn bộ tập dữ liệu huấn luyện.<br>**Mặc định**: 300                                                         |
| 3  | `--batch` <br>or <br>`--batch-size` | **Ý nghĩa**: Kích thước batch, số lượng mẫu sẽ được xử lý trong một lần cập nhật trọng số.<br>**Mặc định**: 16 hoặc 32 (tùy thuộc vào cấu hình phần cứng và script).                                                         |
| 4  | `--data`                    | **Ý nghĩa**: Đường dẫn đến tệp cấu hình dữ liệu, ví dụ như items_datasets.yaml, tệp này chỉ định vị trí của tập huấn luyện, tập kiểm tra, và các lớp của dữ liệu.<br>**Mặc định**: coco128.yaml.                             |
| 5  | `--weights`                 | **Ý nghĩa**: Đường dẫn đến tệp trọng số của mô hình ban đầu, như yolov5s.pt. Nếu không được chỉ định, mô hình sẽ được huấn luyện từ đầu (từ các trọng số ngẫu nhiên).<br>**Mặc định**: Trọng số khởi tạo của mô hình YOLOv5. |
| 6  | `--nosave`                  | **Ý nghĩa**: Nếu chỉ định tùy chọn này, mô hình sẽ không lưu các trọng số cuối cùng sau khi huấn luyện.<br>**Mặc định**: Mô hình sẽ tự động lưu trọng số tốt nhất và cuối cùng.                                              |
| 7  | `--cache`                   | **Ý nghĩa**: Dùng để lưu trữ (cache) hình ảnh trong RAM để tăng tốc độ đọc ảnh trong quá trình huấn luyện.<br>**Mặc định**: Không lưu trữ trong RAM.                                                                         |
| 8  | `--device`                  | **Ý nghĩa**: Chỉ định thiết bị sử dụng để huấn luyện mô hình (ví dụ: 0 cho GPU cụ thể, cpu cho CPU).<br>**Mặc định**: Tự động phát hiện thiết bị (thường là GPU nếu có).                                                     |
| 9  | `--cfg`                     | **Ý nghĩa**: Đường dẫn đến tệp cấu hình của mô hình, nếu bạn muốn tự thiết kế kiến trúc mạng nơ-ron (ví dụ: --cfg yolov5m.yaml để chỉ định mô hình).<br>**Mặc định**: Mô hình YOLOv5 đã được chỉ định qua --weights.         |
| 10 | `--name`                    | **Ý nghĩa**: Tên của phiên bản huấn luyện cụ thể. Tên này sẽ được sử dụng để tạo thư mục lưu kết quả.<br>**Mặc định**: exp (số lượng các thử nghiệm được tăng lên mỗi lần huấn luyện mới).                                   |
| 11 | `--resume`                  | **Ý nghĩa**: Tiếp tục huấn luyện từ một lần huấn luyện trước đó bằng cách chỉ định đường dẫn đến tệp checkpoint (trọng số tạm dừng).<br>**Mặc định**: Huấn luyện mới từ đầu.                                                 |
| 12 | `--notest`                  | **Ý nghĩa**:: Nếu được chỉ định, mô hình sẽ không thực hiện đánh giá (test) sau mỗi epoch.		Mặc định: Mặc định, mô hình sẽ được đánh giá sau mỗi epoch.                                                                     |
| 13 | `--rect`                    | **Ý nghĩa**: Sử dụng cắt hình chữ nhật cho ảnh đầu vào trong khi huấn luyện (thay vì cắt vuông), thường hữu ích cho ảnh có tỷ lệ khác nhau.<br>**Mặc định**: Không sử dụng cắt hình chữ nhật.                                |
| 14 | `--single-cls`              | **Ý nghĩa**: Chỉ định tùy chọn này nếu bạn muốn huấn luyện mô hình cho một lớp duy nhất (ví dụ: tất cả các đối tượng đều thuộc một lớp).<br>**Mặc định**: Huấn luyện nhiều lớp dựa trên cấu hình dữ liệu.                    |
| 15 | `--adam`                    | **Ý nghĩa**: Sử dụng optimizer Adam thay vì optimizer SGD (Stochastic Gradient Descent).<br>**Mặc định**: Sử dụng SGD.                                                                                                       |
| 16 | `--image-weights`           | **Ý nghĩa**: Huấn luyện sử dụng trọng số mẫu dựa trên hình ảnh, ưu tiên các hình ảnh chứa đối tượng.<br>**Mặc định**: Không sử dụng trọng số ảnh.                                                                            |
| 17 | `--sync-bn`                 | **Ý nghĩa**: Sử dụng Batch Normalization đồng bộ giữa các GPU khi huấn luyện trên nhiều GPU.<br>**Mặc định**: Không đồng bộ hóa Batch Normalization.                                                                              |
| 18 | `--workers`                 | **Ý nghĩa**: Số lượng worker cho việc tải dữ liệu, giúp tăng tốc độ tải dữ liệu vào trong quá trình huấn luyện.<br>**Mặc định**: 8.                                                                                          |
| 19 | `--project`                 | **Ý nghĩa**: Chỉ định thư mục để lưu kết quả huấn luyện.<br>**Mặc định**: runs/train.                                                                                                                                        |
| 20 | `--exist-ok`                | **Ý nghĩa**: Nếu thư mục lưu kết quả đã tồn tại, không ghi đè và tiếp tục ghi vào đó.<br>**Mặc định**: Tạo thư mục mới nếu thư mục đã tồn tại.                                                                               |
| 21 | `--evolve`                  | **Ý nghĩa**: Tự động tối ưu các siêu tham số (hyperparameters) trong quá trình huấn luyện.<br>**Mặc định**: Không sử dụng tối ưu siêu tham số.                                                                               |

## Getting Started
### 1. Create Datasets
- [Roboflow](https://roboflow.com/#)
- [Public Datasets](https://universe.roboflow.com/?ref=ultralytics)

### 2. Setup
- Create file **.yaml** in yolov5/data (Example: **threeitems.yaml**)
```threeitems.yaml
# Ultralytics YOLOv5 🚀, AGPL-3.0 license
# Example usage: python train.py --data threeitems.yaml
# parent
# ├── yolov5
# ├── originals
# |   └── threeitems.mp4
# └── datasets
#     └── threeitems  ← downloads and saves the dataset here

# Train/val/test sets as 1) dir: path/to/imgs, 2) file: path/to/imgs.txt, or 3) list: [path/to/imgs1, path/to/imgs2, ..]
path: ../datasets/threeitems        # dataset root dir
train: train/images/                # train images (relative to 'path') xxx images
val: valid/images/                  # valid images (relative to 'path') xxx images
test: test/images/                  # test images (optional)

# Classes (List up label annotated for items when creating datasets)
names:
  0: person 
  1: pen    
```

## 3. Training
### Train
```bash
$ python train.py --img 640 --batch 16 --epochs 100 --data items_datasets.yaml --weights yolov5s.pt --nosave --cache
```

### Detect
```bash
$ python detect.py --weight runs/train/exp3/weights/last.pt --source /.../threeitem.mp4
```
