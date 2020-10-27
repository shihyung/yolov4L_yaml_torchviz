# Yolo_v4L_mish yaml to torchviz Block Diagram  
## 目的:
### Yolo 的 yaml 不容易理解，最好以方塊結構圖(block-diagram)表示，過程可以使用 torchviz 或是 Netron 將 Yolov4 可視化，可以更清楚瞭解 Yolov4 的整體架構。個人比較喜歡用 torchviz 將每個基本單元顯示出來，看看圖片(3,640,640)經過各單元後的維度與尺寸變化。  
### Netron 需要 .pt / .pth / .onnx 等等模型檔案，torchviz 則是加入幾行程式即可轉成 pdf 檔案:
    from torch.autograd import Variable
    from torchviz import make_dot
    
    img = Variable(torch.randn(1, 3, 640, 640))
    out=model(img) #out is a list with length: 3
    vizshow=make_dot(out[0], params=dict(model.named_parameters()))
    #vizshow=make_dot(out[1], params=dict(model.named_parameters()))
    #vizshow=make_dot(out[2], params=dict(model.named_parameters()))
    vizshow.view()
## Yolo_v4L_mish.yaml 架構:
![yolov4L_yaml.png](images/yolov4L_yaml.png)
***
## Yolo_v4L_mish torchviz Visualization:
### ps: 檔案很大，載入需要時間...
![yolov4L_out3.png](images/yolov4_out3.png)
***
# Block Diagram
### 製作中
### 雖然網路上很多方塊結構圖，但自己製作一份能夠更了解 Yolov4 的架構。
