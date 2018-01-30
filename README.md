# tensorflow_models_object_detection  
使用tensorflow的目标检测
## 下载项目
[tensorflow/model](https://github.com/tensorflow/models)  
## 安装
[installation](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md)
## 数据
* [method 1](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/using_your_own_dataset.md)
* method 2  
1. 使用imglabel标注数据,生成pascal格式数据  
   pascal 目录结构
    + data (save pictures)
      + JPEGImages
    + VOC2007 
        + Annotations
        + ImageSets
            + Main
                - test.txt
                - train.txt
                - val.txt
                - trainval.txt
2. copy并修改data/label_map
3. 使用dataset_tools/create_pascal_tf_record.py将1,2步的data,label_map生成tfrecord格式数据  
  error:  /VOC2007/ImageSets/Main/aeroplane_trainval.txt; No such file or directory  
      create_pascal_tf_record.py: 'aeroplane_' + FLAGS.set + '.txt') --> FLAGS.set + '.txt')
## 训练
1. copy并修改对应模型的 sample/configs/*.config 文件
2. 使用train.py训练  
train.py --train_dir='...' --pipeline_config_path='...'
