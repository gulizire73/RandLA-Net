# RandLA-Net
利用RandLA-Net实现室外点云数据语义分割，参考了https://github.com/QingyongHu/RandLA-Net
## 环境配置说明
本项目是在Linux环境下运行
### 安装
1.创建虚拟环境   
conda create -n randlanet python=3.6      
conda activate randlanet      
2.运行以下命令，在conda中安装Tf、CUDA和其他必要Python包      
pip install numpy==1.19.5 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install h5py~=3.1.0 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install cython==0.29.15 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install open3d-python==0.3.0 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install pandas==1.1.5 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install scipy==1.5.4 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install scikit-learn==0.21.3 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install PyYAML==6.0.1 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install tensorflow-gpu==1.15 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
conda install cudatoolkit=11.2 cudnn=8.1 -c=conda-forge   
3.进入RandLA-Net目录  
cd utils/nearest_neighbors/   
python setup.py install --home="."   
cd ../../   
cd utils/cpp_wrappers/cpp_subsampling   
python setup.py build_ext --inplace   

本部分参考了https://zhuanlan.zhihu.com/p/670690151也有部分改动   

## 数据说明
把测试训练数据存在/data/semantic/original_data/目录下，按照以下格式：   
![image](https://github.com/user-attachments/assets/5c7cc67d-deaa-4f0f-a158-057f7d1a802c)   
其中有.labels文件为训练数据，没有.labels文件为测试数据

## 运行说明
1.数据预处理   
python utils/data_prepare_semantic3d.py   
2.模型训练   
python main_Semantic3D.py --mode train --gpu 0   
3.模型测试   
python main_Semantic3D.py --mode test --gpu 0   

## 模型介绍
### 点云标注
使用CloudCompare对点云数据进行标注，分为以下6类：   
![image](https://github.com/user-attachments/assets/06ba9de6-a7d5-4ef9-8ce7-60b582d4ea2d)   
### 参数设置说明
![image](https://github.com/user-attachments/assets/4e2d350a-9557-45d5-b8a1-54e033ccc636)   

![image](https://github.com/user-attachments/assets/b2804517-b982-4ad0-b6f3-6e019f1fb496)   

![image](https://github.com/user-attachments/assets/51fe0d57-fb4f-480b-9f29-0c2ef341ffd4)   

本次项目并没有使用颜色信息

## 模型分割精度
![image](https://github.com/user-attachments/assets/c23ac61e-7f03-46bf-9b7a-1ec763adb047)










